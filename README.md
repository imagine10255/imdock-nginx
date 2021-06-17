imdock-nginx
====================================================

Add the module (njs, http_headers_more) to the official method, and provide the basic template out of the box


## Getting Started
```bash
$ git clone https://github.com/imagine10255/imdock-nginx.git site-dev
$ cd site-dev

# Option (first create network)
$ docker network create --driver bridge imdockgroup

# Starting
$ docker-compose up
```

## Custom Config
add config to docker-compose.yml

```
volumes:
    - "./config/nginx/nginx.conf:/etc/nginx/nginx.conf"
    - "./config/nginx/site-modules:/etc/nginx/site-modules"
    - "./config/nginx/conf.d:/etc/nginx/conf.d"
    - "./public:/etc/nginx/html"
```

## Reference Architecture:

```txt
imdock-nginx
├── config/nginx
|           ├── conf.d           # site config
|           ├── site-module      # site module
|           |    ├── njs         # site module
|           |    └── proxy.conf  # site module
|           └── nginx.conf       # nginx config
├── public                       # site static files
└── docker-compose.yml
```


## Ref
- [use module issue](https://github.com/nginxinc/docker-nginx/issues/511#issuecomment-857555895)
- [use module step](https://github.com/nginxinc/docker-nginx/tree/master/modules#readme)
- [njs sample](https://www.gushiciku.cn/pl/gJu3/zh-tw)
