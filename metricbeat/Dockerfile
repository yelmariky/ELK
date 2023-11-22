# Utilisation d'une image de base de Metricbeat officielle
FROM docker.elastic.co/beats/metricbeat:7.16.3

# Copie du fichier de configuration Metricbeat dans l'image
COPY metricbeat.yml /usr/share/metricbeat/metricbeat.yml

# Démarre Metricbeat lors du démarrage du conteneur
CMD ["metricbeat", "-c", "/usr/share/metricbeat/metricbeat.yml"]
