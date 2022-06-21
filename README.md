# cp-all-in-one-action

This action runs [cp-all-in-one](https://github.com/confluentinc/cp-all-in-one/tree/latest/cp-all-in-one), a Docker Compose for Confluent Platform.  See [Confluent documentation](https://docs.confluent.io/platform/current/tutorials/build-your-own-demos.html) for details.

# Usage

- `service`: up to which service in the docker-compose.yml file to run.  Default is none, so all services are run
- `github-branch-version`: which GitHub branch of [cp-all-in-one](https://github.com/confluentinc/cp-all-in-one) to run.  Default is `latest`.
- `type`: cp-all-in-one (based on Confluent Server) or cp-all-in-one-community (based on Apache Kafka)

Example to run ZooKeeper and Confluent Server on Confluent Platform `7.1.0`:

```yaml

    steps:

      - name: Run Confluent Platform (Confluent Server)
        uses: ybyzek/cp-all-in-one-action@v0.2.1
        with:
          service: broker
          github-branch-version: 7.1.0-post
```

Example to run all Apache Kafka services on `latest`:

```yaml

    steps:

      - name: Run Confluent Platform (Confluent Server)
        uses: ybyzek/cp-all-in-one-action@v0.2.1
          type: cp-all-in-one-community
```

# Ports

To connect to services in Docker, refer to the following ports:

- ZooKeeper: 2181
- Kafka broker: 9092
- Kafka broker JMX: 9101
- Confluent Schema Registry: 8081
- Kafka Connect: 8083
- Confluent Control Center: 9021
- ksqlDB: 8088
- Confluent REST Proxy: 8082

# Example

Example usage at https://github.com/ybyzek/kafka-github-actions
