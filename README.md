# docker-vaultwarden

Minimal Docker Compose configuration for Vaultwarden

Image is based on [Rust implementation of Bitwarden API](https://github.com/dani-garcia/vaultwarden).

**This project is not associated with the [Bitwarden](https://bitwarden.com/) project nor 8bit Solutions LLC.**

---

## Installation

Pull this repository, create configuration file, and then start the services with Docker Compose:

```sh
# Create a copy of the sample .env file
cp .env.dist .env

# Modify the configuration file `.env` if needed

# Start services
docker compose up -d

# Stop services
docker compose down

# If using standalone Docker Compose, use `docker-compose` instead of `docker compose`
```

> It is highly recommended to use a reverse proxy like nginx or Traefik to handle incoming (HTTPS) connections.

---

**IMPORTANT**: Some web browsers, like Chrome, disallow the use of Web Crypto APIs in insecure contexts. In this case, you might get an error like `Cannot read property 'importKey'`. To solve this problem, you need to access the web vault from HTTPS.

This can be configured in [vaultwarden directly](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-HTTPS) or using a third-party reverse proxy ([some examples](https://github.com/dani-garcia/vaultwarden/wiki/Proxy-examples)).

If you have an available domain name, you can get HTTPS certificates with [Let's Encrypt](https://letsencrypt.org/), or you can generate self-signed certificates with utilities like [mkcert](https://github.com/FiloSottile/mkcert). Some proxies automatically do this step, like Caddy (see examples linked above).

## Usage

See the [vaultwarden wiki](https://github.com/dani-garcia/vaultwarden/wiki) for more information on how to configure and run the vaultwarden server.
