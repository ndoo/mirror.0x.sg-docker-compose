# mirror.0x.sg Docker Compose Files

This repository contains the [Docker Compose](https://docs.docker.com/compose/) files used to build the services behind [mirror.0x.sg](https://mirror.0x.sg).

## Requirements

Other than requiring a working Docker + Docker Compose environment, CephFS named volumes are defined in the Compose files for persistent storage, as this is what mirror.0x.sg uses.

If you do not wish to use CephFS, please redefine the volumes to suit your environment; you may also wish to remove the unused CephFS environment variables in the top-level `.env` file.

## Configuration

Edit the top-level `.env` file to define the public IPs the services should bind to, as well as the CephFS connection parameters.

If using proftpd, edit `proftpd/pasv_address.env` to define the public-facing IPv4 address FTP clients will connect to.

## Usage

Open a terminal, `cd` to each folder, and run `docker compose up -d`.

When stopping services, you may also wish to cleanup orphaned volumes with `docker compose down -v`.

