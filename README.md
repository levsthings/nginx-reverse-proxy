<h1 align='center'>Ship An NGINX Reverse Proxy</h1>

## Repository

Latest version: `levsthings/nginx-reverse-proxy:testing`

Image lives [here.](https://hub.docker.com/r/levsthings/nginx-reverse-proxy/). 

## Usage

Include this image in your `docker-compose.yml`:

```yaml
## Example:
version: '3'
services:
    nginx:
        image: 'levsthings/nginx-reverse-proxy:testing'
        links: 
            - app:app
        ports:
            - '80:80'
        networks:
            - frontend
    app:
        build: .
        ports:
            - '3000'
        networks:
            - frontend
networks:
    frontend: null
```