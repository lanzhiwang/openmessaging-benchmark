# The OpenMessaging Benchmark Framework

This repository houses user-friendly, cloud-ready benchmarking suites for the following messaging platforms:

* [Apache Kafka](https://kafka.apache.org)
* [Apache RocketMQ](https://rocketmq.apache.org)
* [RabbitMQ](https://www.rabbitmq.com/)
* [Apache Pulsar](https://pulsar.apache.org)
* [NATS Streaming](https://nats.io/)

> More details could be found at the [official documentation](http://openmessaging.cloud/docs/benchmarks/).

## 使用方法

1. 安装 java 和 maven

- java 版本: `openjdk version "1.8.0_272"`

- maven 版本: `Apache Maven 3.0.5`

2. 编译安装

```bash
mvn install
```

> 编译过程需要下载大量的第三方 jar 包，过程较长，如果出现超时，直接继续执行上面的命令

3. 运行

```bash
# 以 driver-kafka/kafka.yaml 作为驱动文件，1-topic-16-partitions-1kb.yaml 作为负载配置文件
bin/benchmark --drivers driver-kafka/kafka.yaml workloads/1-topic-16-partitions-1kb.yaml
```

* `--drivers` 参数中指定的 yaml 文件说明了 topic、生产者、消费者、一般配置等选项，driver-kafka 目录中的 yaml 文件都可以作为 --drivers 参数值

* `workloads` 目录中的 yaml 指定了性能测试的负载
