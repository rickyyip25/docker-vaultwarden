# docker-vaultwarden
Docker Compose configuration for Vaultwarden

Image is based on [Rust implementation of Bitwarden API](https://github.com/dani-garcia/vaultwarden).

**This project is not associated with the [Bitwarden](https://bitwarden.com/) project nor 8bit Solutions LLC.**

---
## Installation
Pull this repository, create configuration file, and then start the services with Docker Compose:

```sh
cp .env.dist .env
docker compose up -d

# If using standalone docker-compose, run `docker-compose up -d`
```

**IMPORTANT**: Some web browsers, like Chrome, disallow the use of Web Crypto APIs in insecure contexts. In this case, you might get an error like `Cannot read property 'importKey'`. To solve this problem, you need to access the web vault from HTTPS. 

This can be configured in [vaultwarden directly](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-HTTPS) or using a third-party reverse proxy ([some examples](https://github.com/dani-garcia/vaultwarden/wiki/Proxy-examples)).

If you have an available domain name, you can get HTTPS certificates with [Let's Encrypt](https://letsencrypt.org/), or you can generate self-signed certificates with utilities like [mkcert](https://github.com/FiloSottile/mkcert). Some proxies automatically do this step, like Caddy (see examples linked above).

## Usage
See the [vaultwarden wiki](https://github.com/dani-garcia/vaultwarden/wiki) for more information on how to configure and run the vaultwarden server.
