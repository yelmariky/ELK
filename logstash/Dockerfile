FROM docker.elastic.co/logstash/logstash:7.16.3
USER root
COPY logstash.conf /usr/share/logstash/pipeline/logstash.conf
#RUN chown -R 1000:1000 /usr/share/logstash
#RUN chmod -R 777 /usr/share/logstash

USER logstash
# Exécutez Logstash avec votre configuration personnalisée
CMD ["logstash", "-f", "/usr/share/logstash/pipeline/logstash.conf"]