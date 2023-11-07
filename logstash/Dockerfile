FROM docker.elastic.co/logstash/logstash:7.16.3

COPY logstash.conf /usr/share/logstash/pipeline/logstash.conf


# Exécutez Logstash avec votre configuration personnalisée
CMD ["logstash", "-f", "/usr/share/logstash/pipeline/logstash.conf"]