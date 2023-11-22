FROM docker.elastic.co/beats/filebeat:7.16.3
USER root
COPY filebeat.yml /usr/share/filebeat/conf/filebeat.yml
#RUN chown -R 1000:1000 /usr/share/logstash
#RUN chmod -R 777 /usr/share/logstash

USER filebeat
# Exécutez Logstash avec votre configuration personnalisée
CMD ["filebeat", "-c", "//usr/share/filebeat/conf/filebeat.yml"]