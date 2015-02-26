# Logstash "client" in Docker
Docker container with logstash and redis as output
## Run
```
docker run -d -v logs/nginx:/var/log/nginx -v logs/varnish:/var/log/varnish --add-host="redis:<ip>" <id>
```
* ip = is redis ip
* id = is docker image id

## Nginx log
Nginx logs are read from files in /var/log/nginx
### log_format directive
```
log_format combinedwithservername
                '$remote_addr - $remote_user [$time_local] '
                '"$request" $status $body_bytes_sent '
                '"$http_referer" "$http_user_agent" '
                '$server_name "$sent_http_content_type" $request_time';
```
## Varnish log
Varnish logs are read from files in /var/log/varnish
Example :
```
86.220.15.188 - - [23/Feb/2015:14:31:29 +0100] "GET http://dev.petitchevalroux.net/favicon.ico HTTP/1.1" 200 0 "-" "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/40.0.2214.115 Safari/537.36"
``

Available on:
* [docker hub](https://registry.hub.docker.com/u/petitchevalroux/logstash/)
* [github](https://github.com/petitchevalroux/docker-logstash)

## About me
http://petitchevalroux.net