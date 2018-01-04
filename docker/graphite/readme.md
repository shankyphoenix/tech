https://hub.docker.com/r/alexmercer/graphite-grafana/
sudo docker run -v /var/www/html/docker/graphite:/var/lib/graphite/storage/whisper \
           -v /var/www/html/docker/grafana/data:/usr/share/grafana/data \
           -p 2003:2003 -p 3000:3000 -p 8180:80\
           -d alexmercer/graphite-grafana

sudo docker run -d --name=grafana -p 3000:3000 grafana/grafana

sudo docker run -d\
 --name graphite\
 --restart=always\
 -p 8180:80\
 -p 2003-2004:2003-2004\
 -p 2023-2024:2023-2024\
 -p 8125:8125/udp\
 -p 8126:8126\
 hopsoft/graphite-statsd

 sudo chown -R www-data:suntec ./docker/*
