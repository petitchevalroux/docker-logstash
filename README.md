# Logstash "client" in Docker
Docker container with logstash and redis as output
## Run
```
docker run -d -v logs/nginx:/var/log/nginx --add-host="redis:<ip>" <id>
```
* ip = is redis ip
* id = is docker image id

## Nginx log
Nginx log are read from file in /var/log/nginx
### log_format directive
```
log_format combinedwithservername
                '$remote_addr - $remote_user [$time_local] '
                '"$request" $status $body_bytes_sent '
                '"$http_referer" "$http_user_agent" '
                '$server_name';
```

Available on:
* [docker hub](https://registry.hub.docker.com/u/petitchevalroux/logstash/)
* [github](https://github.com/petitchevalroux/docker-logstash)

## About me
http://petitchevalroux.net