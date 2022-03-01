# Descripción

Este proyecto consiste en portar mi _legacy config_ de Ansible, hacerlo más extensible y configurarlo correctamente.
El estado actual se podrá ver en el repositorio de Ansible en Gitea (replicado en Github).

### Objectivos:
- Automatizar provisión de server _Dionisio_, con todos sus containers en Docker.
- Ejecución remota de configuración a partir de Gitea+Drone.
- Testing de todos los roles usando Molecule.
- Portabilidad mediante el uso de variables globales.
- Protección de contraseñas y secretos a partir de Ansible Vault.
- Optimizar backup de databases.

## Estructura

**Ansible**
- [ ] Configurar test con Molecule.
- [ ] Configurar Drone

**Conectividad**
- [ ] Configurar DNS de Cloudflare con Ansible.
  - [X] Para francocalvo.ar.
  - [ ] Para fjc.ar.

### Zeus

**Provisioning**
- [ ] Agregar configuración general de discos. ([ver](https://github.com/FuzzyMistborn/infra/tree/main/roles/adonalsium))
- [ ] Configurar repositorios correspondientes de Proxmox.
- [ ] Instalar configuración de Neovim.

**Configurar filesystem de VMs**
- [ ] Instalar y configurar MergerFS.
- [ ] Instalar y configurar SnapRAID.
- [ ] Instalar y configurar Kopia.
- [ ] Instalar y configurar Samba.

**Conectividad**
- [ ] Instalar y configurar Wiregurd.

**Automatización**
- [ ] Agregar cronjobs.
- [ ] Instalar y configurar Ansible.

---

### Dionisio

**Provisioning**
- [ ] Instalar configuración de Neovim.
- [X] Agregar Samba en red.

**Docker**
- [X] Instalar Docker.
- [X] Instalar docker-compose.
- [ ] Configurar dumps y backups de bases de datos.

**Contenedores**
- [ ] Authentik.
- [ ] Code-server.
- [ ] Duplicati.
- [X] Drone.
- [X] Gitea.
- [X] Haste-server.
- [ ] Jellyfin.
- [ ] JFA.
- [ ] Librespeed.
- [ ] Nextcloud.
- [ ] Minio.
- [ ] Outline.
- [ ] Paperless.
- [ ] Photoprism.
- [X] Portainer.
- [ ] qBittorrent.
- [X] Redbot.
- [ ] Swag.
  - [X] Proxy configurations.
  - [X] Nginx configurations.
  - [X] Testing with Cloudflare.
  - [ ] Wrap up configuration.
- [ ] Syncthing.
- [X] Automation:
  - [X] Radarr.
  - [X] Sonarr.
  - [X] Bazarr.
  - [X] Prowlarr.
  - [X] Ombi.
  - [X] Unmanic.

