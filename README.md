# ELK Setup Based on Docker
Docker based ELK deployement

Keep all the files under one folder and run docker-compose up

Make sure you have docker and docker-compose installed in your env

Access your ELK instance via : http://localhost:5601 

username : elastic
Password : StrongPassword

Which is ELASTIC_PASSWORD, If you havent changed ,then it is "StrongPassword"

Please change password in docker-compose.yml , which is ELASTIC_PASSWORD variable
Required same in kibana.yml , logstash.yml as well... 

Play with ELK .. Enjoy

If you are facing problem with windows docker ,Like drive mapping , make sure you build container with below settings and mention same in docker-compose.yml



FROM kibana:7.4.0
ADD kibana.yml /usr/share/kibana/config/kibana.yml
EXPOSE 5601


FROM logstash:7.4.0
ADD logstash.yml /usr/share/logstash/config/logstash.yml
EXPOSE 5000
EXPOSE 9600


FROM elasticsearch:7.4.0
ADD elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml
EXPOSE 9200
EXPOSE 9300
