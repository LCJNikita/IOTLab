### Task 1

(см. docker-compose.yaml; sourceTopic, destinationTopic для Kafka Connectors)

Чтобы запустить контейнеры, выполните команду:
`./start.sh`

Для подключения к узлам MongoDB используйте следующие команды:

Source node:

`docker exec -it mongo1 /bin/bash`: для подключения к узлу mongo1

Затем выполните команду: `mongosh "mongodb://mongo1"`

Target node:

`docker exec -it mongo2 /bin/bash`: для подключения к узлу mongo2

Затем выполните команду: `mongosh "mongodb://mongo2"`


Пример ввода данных: 

`db.users.insertOne({ firstname: "nik", lastname: "kuz", age: 22, email: "nik@gmail.com" })`

### Task 2

(улучшен sourceTopic: добавлен параметр schema)

`db.users.insertOne({ firstname: "nik", lastname: "kuz", age: 22, email: "nik@gmail.com" })`

### Task 3

(см. docker-compose.yaml)

Чтобы запустить контейнеры, выполните команду:

`./start.sh`

Чтобы увидеть изменения БД после публикации данных: 

`docker exec -it clickhouse-kafka-server-1 clickhouse-client`

Остановка контейнеров:

`docker-compose -p mongo-kafka down`

`docker-compose -p clickhouse-kafka down`

Остановка контейнеров и удаление образов:

`docker-compose -p mongo-kafka down --rmi all`

`docker-compose -p clickhouse-kafka down --rmi all`