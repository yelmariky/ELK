# Utilisation d'une image de base de Metricbeat officielle
FROM docker.elastic.co/elasticsearch/elasticsearch:7.16.3

# Copie du fichier de configuration Metricbeat dans l'image
COPY elasticsearch.yml /usr/share/elasticsearch/config/

# Démarre Metricbeat lors du démarrage du conteneur
##CMD ["elasticsearch", "-c", "/usr/share/elasticsearch/config/elasticsearch.yml"]
