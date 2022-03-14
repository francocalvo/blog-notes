# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Overview](#Overview)
  - [Endpoint types](#Overview#Endpoint types)
- [Stages](#Stages)
  - [Stage Variables](#Stages#Stage Variables)
  - [Configurations](#Stages#Configurations)
    - [Canary Deployment](#Stages#Configurations#Canary Deployment)
- [Integration types](#Integration types)
  - [Mapping templates](#Integration types#Mapping templates)
- [Swagger / Open API specifications](#Swagger / Open API specifications)
- [Caching API responses](#Caching API responses)
  - [Cache Invalidation](#Caching API responses#Cache Invalidation)
- [Usage Plans & API Keys](#Usage Plans & API Keys)
- [Logging & Tracing](#Logging & Tracing)
  - [Errors](#Logging & Tracing#Errors)
- [Security](#Security)
  - [CORS or Cross-Origin Resource Sharing](#Security#CORS or Cross-Origin Resource Sharing)
  - [IAM Permissions](#Security#IAM Permissions)
  - [Cognito User Pools](#Security#Cognito User Pools)
  - [Lambda Authorizer](#Security#Lambda Authorizer)
- [HTTP API and REST API](#HTTP API and REST API)

</div>
{{<toc>}}

# Overview

If you would want to create a serverless API, you can create a CRUD interface
between Lambda and DynamoDB. But we would like our clients to invoke our lambda
function.

For this, we can use a **API Gateway**, which allows us to create REST APIs
that are going to be public and accesible for out clients. This API will proxy
the requests to our functions.

Some benefits are:

- No infra to manage.
- Support for the WebSocket protocol.
- Can handle API versioning.
- Handle different environments.
- Handle security with Authentication and Authorization.
- Create API keys, handle requests throttling.
- Swagger/Open API import to quickly define APIs.
- Transform and validate requests and responses.
- Generate SDK and API specifications.
- Cache API responses.

The integrations normally are:

- Lambda function: allows us to invoke a lambda function, which is an easy way
  to expose a REST API backed by AWS Lambda.
- HTTP: expose an HTTP endpoint in the backend, like an internal API.
- AWS Service: expose any AWS API through the Gateway.

## Endpoint types

- **Edge-optimized** for global clients, requests are routed through the
  CloudFront Edge locations, but the API still lives in one location.
- **Regional** for clients within the same region, and could be manually
  combined with CloudFront.
- **Private** can only be accessed from your VPC using an interface VPC
  endpoint.

# Stages

Making changes in the API Gateway isn't effective until we do a **deployment**.
Changes can be deployed to "Stages", like dev, prod, test, etc. Each stage has
its own configuration parameters and they can be rolled back as a history is
kept.

This is very useful, as it allows us to create different stages for different
version of our API.

## Stage Variables

It's used to control often changing configuration values, and can be used in
Lambdas ARN, HTTP endpoint, parameter mappings, etc.

They are useful because it lets us:
- Configure HTTP endpoints your stages talk to.
- Pass configurations parameters to AWS Lambda through mapping templates.

Also, we can use it to connect them to **Lambda aliases**. We can create a
stage variable to indicate the corresponding Lambda and our API will invoke the
right Lambda function.

To achieve this, when we create a GET method, in the Lamba function name, we
can append this: `lambda-name:${stageVariables.lambdaAlias}`, where we can
create a stage variable. Then, will need to execute a command in the CLI to
change the permissions in the Lambda for each alias.

To check for this, in the Test environment of the API, you can specify the
Stage Variables, or when you deployed your API stage, you can specify a Stage
Variable for it.

## Configurations

For each stage we have settings we can change, like throttling, WAF or client
certificate.

### Canary Deployment

This allows us to route a given % of traffic to the canary channel. This is
useful to start testing a new version of the Lambda function behind.

This allows also to have separate metrics&logs and possibility to override any
stage variable, allowing us to do a blue/green deployment with AWS Lambda & API
Gateway.


# Integration types

We have different types to integrate to our backend. These are:

- **MOCK:** the API returns a responde without sending the request to the
  backend. This is use for development or testing.
- **HTTP/AWS:** the API will forward a request, but we can modify it. In this
  case we need to configure both the integration request and integration
  responde. This means setting up data mapping using *mapping templates*.
- **Lambda proxy:** it's the one we talked about, where the API forwards the
  request to a Lambda Function, where the incoming request from the client is
  the input to the Lambda. This means the Lambda is responsible for the logic
  of request/response.
- **HTTP proxy:** it works like the Lambda proxy but for HTTP requests.

## Mapping templates

These can be used for modifying the request or response of the API, rename
query string parameters, modify the body content, add headers, etc. buy the VTL.

For example, in an HTTP request, if we got the following:

```
http://example.com/path?name=foo&other=bar
``` 

We can use a mapping to change the query string to the following JSON;

```JSON
{ "my_variable":"foo","other_variable":"bar"}
```

To use this, we can't use the Proxy function of the GET method, and we have to
handle the response JSON and request JSON. To see a Hand-on watch Lesson 349.


# Swagger / Open API specifications

These are common ways of defining REST APIs, using API definition as code. We
can import an existing Swagger/OpenAPI 3.0 spec to API Gateway.

Can be useful to migrate current configurations to API Gateway.

# Caching API responses

It allows us to reduce the number of calls made to the backend. The TTL by
default is 300 seconds, and the max is 3600s.

These are defined at the stage level, so we have one cache per stage, and we
can even override cache settings per method. It only makes sense in prod as
it's expensive.

## Cache Invalidation

From the UI we can invalidate it immediately (flush it). Also, the clients with
the correct authorization can invalidate the cache with the header
`Cache-Control:max-age=0`. When we allows for the last, we need to impose a
InvalidateCache police, or any client can invalidate the API cache.

# Usage Plans & API Keys

If you want to make your API available, you can create a Usage Plan, you can
modify this:

- who can access one or more deployed API stages and methods.
- how much and how fast they can access them.
- uses API keys to identify API clients and meter access.
- configure throttling limits and quita limits that are enforced per client.

Also we can create API keys, which allow us tu use the Usage Plans to control
access. To create one we need to:

1. Configure a usage plan.
2. Create at least one API, configure the methods to require an API key, and
   deploy the APIs to stages.
3. Generate or import API keys to distribute to application developers who will
   be using your API.
4. Create the usage plan with the desired throttle and quota limits.
5. Associate API stages and API keys with the usage plan.

To see a hands-on watch Lesson 352.
Most importantly, we need to have in the request header a `X-API-Key` with the
value of the API Key.

# Logging & Tracing

We can use CloudWatch logs, which:
- Enable logging at the Stage Level.
- Can override settings on a per API bases.
- Log contains information about request/response body.

We can also use X-Ray, which allows us to:
- Enable tracing to get extra information about requests in API Gateway.
- X-Ray API Gateway + AWS Lambda gives you the full picture.

In CloudWatch Metrics, we should also know:
- Metrics are by stage, possibility to enable detailed metrics.
- CacheHitCount & CacheMissCount: allows us to see the efficiency of the cache.
- Count: number of API requests in a given period.
- IntegrationLatency: time between when the API Gateway relays a request to the
  backend and then it receives a response from it.
- Latency: it's the time between a request and a response from the API Gateway.
  It includes the integration latency and other overhead from the API.

For throttling, per account there is a softcap of 10000 req/sec across all
APIs. It means that if one API is under heavy load, it can throttle other APIs.
This will present responses with **429 Too Many Requests**.

Also, you can set a Stage and Method limit to improve performance.

## Errors

The types of errors are:

- **4xx means Client errors**:
  - 400: Bad request.
  - 403: Access denied, WAF filtered.
  - 429: Quota exceeded.
- **5xx means Server Errors**:
  - 502: Bad Gateway Exception, usually for an incompatible output returned
    from a Lambda proxy.
  - 503: Service Unavailable Exception.
  - 504: Integration Failure - example: endpoint request timed-out exception.

# Security
## CORS or Cross-Origin Resource Sharing

CORS must be enable when you receive API calls from another domain. The OPTIONS
pre-flight request must contain the followin headers:

- Access-Control-Allow-Methods.
- Access-Control-Allow-Headers.
- Access-Control-Allow-Origin.

This can be enabled through the Console. The pre-flight request is used to see
if the site is allowed to do a cross origin request, and if all goes well the
client can do the request.

To do this, we can enable CORS per method, and even enable it just to one
specific website. In Proxy Lambda you'll need to add the following header to
the Lambda response

```
Access-Control-Allow-Origin`: "*"
```

## IAM Permissions

You can create an IAM policy authorization and attach to User/Role. This is the
optimal way for internal use. The authentication is done by IAM and the
authorization by IAM Policy. It's useful to leverage "Sig v4" capability where
IAM credential are in headers.

You can also use **Resource Policies**, which allow to set adjacent policy on
your API to define who and what can access it. It's main use is to allow for
cross account access, specific source IP addresses or allow just for a VPC
Endpoint.

## Cognito User Pools

- Fully manages user life cycle, token expires automatically.
- API verifies identity automatically from AWS Cognito.
- No custom implementation needed.
- The authentication is done by Cognito and the authorization by API methods.

## Lambda Authorizer

- It's the most flexible, based in a token-based authorizer like Oauth. 
- We can pass a request with headers or query strings into a Lambda Authorizer.
- The Lambda will evaluate the request and return an IAM policy for the user,
  which is cached.

# HTTP API and REST API

The HTTP APIs allows us to create a low-latency, cost effective AWS Lambda
Proxy, HTTP proxy APIs and private integration. For authorization, it supports
OIDC and OAuth 2.0, and built-in support for CORS.



