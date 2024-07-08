WIP.  Used to run aspace backing services (mysql and solr) in containers.  Docker Desktop not required.

# Prerequisites for running with Colima/Docker CLI (recommended)
1. Install colima (homebrew recommended): https://github.com/abiosoft/colima
2. Install docker cli via brew: `brew install docker`
3. Install docker-compose via brew: `brew install docker-compose`
4. Start colima: `colima start`

# Quick Start
1. From the root dir of this repo, `docker compose up` (add `-d` flag to run in background/detached)
    * NOTE: On first startup solr will come up without a core, shut down, then restart again with the new archivessspace core applied.  Give it *time* on the very first startup.  You may also wish to skip running in detached mode so that you can follow along in the logging during this startup process.

# Stop without removing containers
1. Stop containers with `docker compose stop`
2. Stop colima with `colima stop`

# Stop and remove all containers
1. `docker compose down`
2. Stop colima with `colima stop`

# Stop and remove all containers and volumes (aka blow everything away)
1. `docker compose down -v`
2. Stop colima with `colima stop`