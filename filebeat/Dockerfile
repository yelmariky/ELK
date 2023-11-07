# Utilisez une image de base légère, par exemple Alpine Linux
FROM docker.elastic.co/beats/filebeat:7.16.3

# Copiez votre configuration Filebeat dans le conteneur
COPY filebeat.yml /etc/filebeat/filebeat.yml

# Exécutez Filebeat avec la configuration
CMD ["-e", "-c", "/etc/filebeat/filebeat.yml"]
