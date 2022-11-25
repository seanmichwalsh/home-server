# Sean's Home Server Configuration

## Overview
One of my hobbies is managing my own home server of self-hosted open source applications. I enjoy self-hosting since it helps me to reduce my reliance on privacy-violating online services, directly control my own data, and learn about basic devops / infra tools. I currently deploy my server applications as Docker containers on an Ubuntu 22.04 personal server.


This repository serves to document my specific configuration files for individual applications. Private configuration data has been redacted as env variables.

## Applications

### Traefik
[Traefik](https://doc.traefik.io/traefik/) is the reverse-proxy for my server. It works as the frontline service clients interface with, directing them to the appropriate application. Its benefit over the popular Apache HTTPd web server it its ability to detect and synchronize various application configuration files (including Docker files).

**Containers:**
- `traefik` - Dashboard + proxy

## Nextcloud
[Nextcloud](https://nextcloud.com/) is my cloud file sync server. It also serves as a WebDAV server for my contacts / calendars / tasks, and provides plugins for tools like notes.

**Containers:**
- `nextcloud-db` - Persistent MariaDB instance
- `nextcloud-redis` - Persistent caching service
- `nextcloud-app` - Nextcloud server
