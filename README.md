## ELK
# instal filebeats
# create logs into /users/xxxx/filebeats/logs/{tagLogs} to be associate into pvc
# build docker
docker build -t filebeats-younes:tag .
# build pvc and pv
kubectl apply -f k8s/Persistent*.yml
# build deployment
image: filebeats-younes:tag
kubectl apply -f filebeats.yml

# instal logstash
# build docker
docker build -t logstash-younes:tag .
# build deployment
image: logstash-younes:tag
kubectl apply -f logstash.yml
