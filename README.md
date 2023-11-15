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
# instal kafka
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
# config kafka
helm install -f values kafka/values.yaml kafka-v1 bitnami/kafka 
** To connect a client to your Kafka, you need to create the 'client.properties' configuration files with the content below:



** To create a pod that you can use as a Kafka client run the following commands:

    kubectl run kafka-v1-client --restart='Never' --image docker.io/bitnami/kafka:3.6.0-debian-11-r1 --namespace default --command -- sleep infinity
   # kubectl cp --namespace default kafka/client.properties kafka-v1-client:/tmp/client.properties
    kubectl exec --tty -i kafka-v1-client --namespace default -- bash
    ** TOPIC CREATION
    kafka-topics.sh --bootstrap-server kafka-v1.default.svc.cluster.local:9092 --create --topic demo-elk-logstash --partitions 3 --replication-factor 1


    PRODUCER:
        kafka-console-producer.sh \
            --broker-list kafka-v1-controller-0.kafka-v1-controller-headless.default.svc.cluster.local:9092,kafka-v1-controller-1.kafka-v1-controller-headless.default.svc.cluster.local:9092,kafka-v1-controller-2.kafka-v1-controller-headless.default.svc.cluster.local:9092 \
            --topic demo-elk-logstash

    CONSUMER:
        kafka-console-consumer.sh \
            --bootstrap-server kafka-v1.default.svc.cluster.local:9092 \
            --topic test \
            --from-beginning
