*This is a fork of https://github.com/getredash/setup and requires additional manual steps to run.*

## Changes from parent repo

- Remove lines from `~/.profile` so that docker-compose can be used along side other docker containers.
- Remove nginx service from `data/docker-compose.yml`
- Change `setup.sh` to use `data/docker-compose.yml` instead of Github version.
- Include a template nginx config file (`redash.nginx`) for use with the host machine's nginx installation.

## Setup

1. Install nginx.

1. Run the following:
    ```
    bash setup.sh
    sudo cp data/redash.nginx /etc/nginx/sites-available
    sudo ln -s /etc/nginx/sites-available/redash.nginx /etc/nginx/sites-enabled/redash.nginx
    ```

1. Update the domain name in `/etc/nginx/sites-enabled/redash.nginx`.

1. Add SSL using certbot