# What is Kafka?

It is a distributed even streaming platform used to publish, store, and process real-time data streams. It can be considered as a high-throughoutpit messaging system where different systems(producers and consumers) can comunicate asynchronously.

## Key Concepts:

**Producer** → Sends data (events/messages)

**Consumer** → Reads data

**Topic** → Category or stream of data

**Partition** → Splits topics for scalability

**Broker** → Kafka server that stores data

**Offset** → Unique ID for each message in a partition

## Pros for use:

Kafka is widely used because it is:

**Fast** (handles millions of events per second)

**Scalable** (horizontal scaling via partitions)

**Fault-tolerant** (replication across brokers)

**Durable** (data persisted on disk)

Kafka enables event driven architecture

kafka decouples ysstems and improves scalability

it supports real-time stream processing with tools like kafka streams.

## What problem does Kafka solve?

Kafka solves the problem of reliable, scalable, real-time data streaming between systems. It decouples producers and consumers, allowing systems to communicate asynchronously without direct dependencies.

## How does Kafka ensure fault tolerance?

Kafka uses replication:

Each partition has a leader and followers

If the leader fails, a follower becomes the new leader

Data is replicated across brokers to prevent loss

## What is a partition in Kafka?

A partition is a subset of a topic that allows Kafka to:

Scale horizontally

Process data in parallel

Each partition maintains ordered messages, but ordering is not guaranteed across partitions.

## What is the role of offsets?

Offsets are unique identifiers for messages within a partition.
Consumers use offsets to:

Track progress

Replay messages if needed

## How is Kafka different from traditional message queues?

Kafka stores messages for a configurable time (not deleted after consumption)

Consumers can re-read messages

Designed for high throughput and distributed systems

Traditional queues (like RabbitMQ):

Delete messages after consumption

Focus more on task processing than streaming

## What is a consumer group?

A consumer group is a set of consumers that:

Share the workload of reading from a topic

Each partition is consumed by only one consumer in the group

This enables parallel processing and scalability.

## What is Kafka’s delivery guarantee?

Kafka supports:

At most once (no retries)

At least once (possible duplicates)

Exactly once (with idempotent producers and transactions)

## When would you use Kafka vs a REST API?

Use Kafka when:

You need real-time streaming

Systems should be loosely coupled

High throughput is required

Use REST when:

You need synchronous request-response

Immediate response is required

## What happens if a consumer fails?

Another consumer in the same group takes over the partitions

Consumer resumes from the last committed offset

## Analogy

Kafka is like a commit log, producers drop messages onto it, consumers can pick them up at their own pace, and in the mean time it keeps moving and stores history.
