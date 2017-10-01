<h1 align='center'>Ship An NGINX Reverse Proxy</h1>

## Repository

Latest version: `levsthings/nginx-reverse-proxy`

Image lives [here.](https://hub.docker.com/r/levsthings/nginx-reverse-proxy/)

## Usage

Include this image in your `docker-compose.yml`:

```yaml
## Example:
version: '3'
services:
    nginx:
        image: 'levsthings/nginx-reverse-proxy'
        links: 
            - app:app
        ports:
            - '80:80'
        networks:
            - frontend
    ## Minimum settings of the app you'll reverse proxy to:
    app:
        build: .
        ports:
            - '3000'
        networks:
            - frontend
networks:
    frontend: null
```