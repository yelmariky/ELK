# build docker
docker build -t logstash-younes:1.4 .
# build pvc and pv
kubectl apply -f k8s/Persistent*.yml
# build deployment
image: logstash-younes:1.4
kubectl apply -f logstash.yml
