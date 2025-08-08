A repository used to hold shared workflows, actions, backing services, and other tbd utilities for managing, testing,
and local development related to ArchivesSpace at the Smithsonian.  As a general rule of thumb, if you find yourself
copying the same thing across multiple SI ASpace repositories, rather than copy-pasting, put it here.

## Shared Github Workflows and Actions
See: .github

In order to avoid duplicating common actions across multiple repositories, we've abstracted out reusable workflows
and actions into this repository.  Detailed documentation, including examples on calling these actions, is maintained 
in this repository's Wiki.

## Backing services  
See: docker-compose.yml

Can be used in place of the ASpace core Docker containers for mysql and solr, should that be desired.  Whether using
this compose file, or that in core ArchivesSpace, Docker Desktop is not required.

# Prerequisites for running with Colima/Docker CLI (recommended) on MacOS
1. Install colima (homebrew recommended): https://github.com/abiosoft/colima
2. Install docker cli via brew: `brew install docker`
3. Install docker-compose via brew: `brew install docker-compose`
4. Start colima: `colima start`
   * Additional colima configuration options are available in the [README.md](https://github.com/abiosoft/colima/blob/main/README.md), but you may wish to add additional CPUs
   and memory for best results with ASpace: `colima start --cpu 4 --memory 8`

# Quick Start
1. From the root dir of this repo, `docker compose up` (add `-d` flag to run in background/detached)
    * NOTE: On first startup solr will come up without a core, shut down, then restart again with the new archivessspace core applied.  Give it *time* on the very first startup.  You may also wish to skip running in detached mode so that you can follow along in the logging during this startup process.

## A note on Solr schema versions
The `solr/` dir present in this repo comes from our current ASpace production version (v4.1.0).  If you wish to run against a different version, you can overwrite this dir like so:
```
mkdir newconfig && cd newconfig
git clone --no-checkout https://github.com/Smithsonian/archivesspace.git --branch <desired_tag_version> --depth=1 .
git sparse-checkout init --no-cone
git sparse-checkout set solr/solrconfig.xml solr/schema.xml solr/stopwords.txt solr/synonyms.txt
git checkout
mv solr/* ../solr
cd ..
rm -rf newconfig
```

# Stop without removing containers
1. Stop containers with `docker compose stop`
2. Stop colima with `colima stop`

# Stop and remove all containers
1. `docker compose down`
2. Stop colima with `colima stop`

# Stop and remove all containers and volumes (aka blow everything away)
1. `docker compose down -v`
2. Stop colima with `colima stop`
