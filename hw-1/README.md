#### 1. Запустить контейнеры kafka
```
docker-compose -f kafka.yaml up
```
![](./screenshot/docker-ps.png)

#### 2. Проверить доступность
```
nc -vz 127.0.0.1 19092
```
![](./screenshot/nc.png)

#### 3. Создать topic и прочитать данные из него
```
kafka-topics --create —-bootstrap-server 127.0.0.1:9092 --replication-factor 3 --partitions 8 --topic test
```
```
kafka-topics —-describe —bootstrap-server 127.0.0.1:9092
```
```
kafka-console-consumer —-bootstrap-server localhost:9092 --topic test --from-beginning
```
![](./screenshot/producer-consumer.png)
#### 4. Создать topic и прочитать данные из него через consumer group
![](./screenshot/consumer-group.png)
