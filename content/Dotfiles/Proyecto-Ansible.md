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
- [ ] Agregar secretos con Ansible Vault.
- [ ] Agregar variables globales.
- [ ] Configurar Drone.

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
- [ ] Agregar Samba en red.

**Docker**
- Instalar Docker.
- Instalar docker-compose.
- Configurar dumps y backups de bases de datos.

**Contenedores**
- [ ] Authentik.
- [ ] Duplicati.
- [ ] Drone.
- [ ] Gitea.
- [ ] Glances.
- [ ] Haste-server.
- [ ] Jellyfin.
- [ ] Librespeed.
- [ ] Nextcloud.
- [ ] Outline.
- [ ] Paperless.
- [ ] Photoprism.
- [ ] Portainer.
- [ ] qBittorrent.
- [ ] Redbot.
- [ ] Swag.
- [ ] Syncthing.
- [ ] Automation:
  - [ ] Radarr.
  - [ ] Sonarr.
  - [ ] Bazarr.
  - [ ] Prowlarr.
  - [ ] Ombi.
  - [ ] Unmanic.

