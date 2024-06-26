# Deploy Kafka on K8s

<p>Prerequisite: Kubectl, Kompose<p>
<p>Run the following command to translate docker compose to deployment and service yaml<p>

```
kompose convert
```

<p>Create deployments and services<p>

```
kubectl apply -R -f /home/vagrant/kafka_workspace/test_multi_broker
```

<p>Delete deployments and services<p>

```
kubectl delete deployments/zookeeper deployments/kafka1 deployments/kafka2 deployments/kafka3 services/zookeeper services/kafka1 services/kafka2 services/kafka3 pvc/zookeeper-claim0 pvc/zookeeper-claim1 pvc/kafka1-claim0 pvc/kafka2-claim0 pvc/kafka3-claim0
```

<p>Find file<p>

```
find . -name "*console*"
```

<p>View msg<p>

```
./usr/bin/kafka-console-consumer --bootstrap-server 192.168.56.61:30001 --topic test --from-beginning
```

<p>Create topic<p>

```
./usr/bin/kafka-topics --create --topic test-url-1504 --partitions 3 --replication-factor 3 --bootstrap-server 192.168.56.61:9091
```

<p>List topic<p>

```
./usr/bin/kafka-topics --list --bootstrap-server 192.168.56.61:9091
```

<p>Describe topic<p>

```
./usr/bin/kafka-topics --describe --topic test-url-1504 --bootstrap-server 192.168.56.61:9091
```