# ars-caddy-dev-https
simple local https setup for development purpose based on docker, caddy, and mkcert

# How to use
## Prerequisite
* [mkcert](https://github.com/FiloSottile/mkcert)
* [docker](https://docs.docker.com/get-docker/)
* docker-compose

## Step by Step
1. Install the prerequisites
2. Run mkcert install `mkcert -install`
3. Create new cert for your desired hostname `mkcert example.com "*.example.com"`
  * It will generate e.g `example.com+1.pem` & `example.com+1-key.pem`
  * Place it in the `certs` directory
4. Create Caddyfile, place it in the root of this directory alongside the docker-compose.yml
  * you can use the Caddyfile.base to as a base for your config
  * there is some working example in Caddyfile.sample
    * hostname = alan.dev, with app running on port 9000 
5. Run `docker-compose up` and it's done!
  * PS the container is configured to always restart so you won't need to redo this, and your `https://example.com` can be accessed everytime you startup your machine, make sure your app is running on the configured port!

## Reference
https://codewithhugo.com/docker-compose-local-https/
