# Piwigo on Docker on ProxMox

<p align="center">
    <img height="200" alt="Piwigo Logo" src="img/logo_piwigo.svg">
    <img height="200" alt="Docker Logo" src="img/logo_docker.png">
    <img height="200" alt="ProxMox Logo" src="img/logo_proxmox.png">
</p>

Create a [ProxMox](https://www.proxmox.com/en/) LXC container running Ubuntu and [Piwigo](https://piwigo.org/) on [Docker](https://www.docker.com/).

Tested on ProxMox v7, Docker 20.10.

## Usage

SSH to your ProxMox server as a privileged user and run...

```shell
bash -c "$(wget --no-cache -qLO - https://raw.githubusercontent.com/noofny/proxmox_piwigo/master/setup.sh)"
```

## Optional Post-Setup Steps

1. Append to LXC `/etc/pve/nodes/{NODE_ID}/lxc/{CONTAINER_ID}.conf`

```text
mp0: /mnt/nobackup,mp=/mnt/nobackup,backup=0
mp1: /mnt/photos,mp=/mnt/photos,backup=0
mp2: /mnt/images,mp=/mnt/images,backup=0
```

## Links

- [linuxserver/piwigo](https://github.com/linuxserver/docker-piwigo)
