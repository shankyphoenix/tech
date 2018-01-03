https://hub.docker.com/r/alexmercer/graphite-grafana/
sudo docker run -v /var/www/html/docker/graphite:/var/lib/graphite/storage/whisper \
           -v /var/www/html/docker/grafana/data:/usr/share/grafana/data \
           -p 2003:2003 -p 3000:3000 -p 8180:80\
           -d alexmercer/graphite-grafana

 sudo chown -R www-data:suntec ./docker/*
