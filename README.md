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
### varnishncsa log format option (-F)
see: [how to make it works on debian wheezy](http://blog.onetechnical.com/2014/05/02/hacking-up-varnish-logging-on-ubuntu-12-04/)
```
"%h %l %u %t \"%r\" %s %b \"%{Referer}i\" \"%{User-agent}i\" \"%{Content-type}o\" %D"
```

Available on:
* [docker hub](https://registry.hub.docker.com/u/petitchevalroux/logstash/)
* [github](https://github.com/petitchevalroux/docker-logstash)

## About me
http://petitchevalroux.net