# What is Rabbitmq?

It is a message broker that enables application communication by sending and recieving messages through queues.

It implements AMQP(Advanced Message Queing Protocol) which defined how messages ar epassed between systems

In simple terms it acts as a middleman that delivers messages between services.

## Why is RabbitMq Used?

Decouple systems so producers and consumers dont need to know about each other
makes systems more flexible and maintainable

Handle Asynchronous tasks
background jobs can do emails, payments, notifications
prevents blocking of your main application

ensure reliable delivery
messsages can be aknowledged, retried and persisted to disk

load balancing distributes taskas across multiple workers
smoothens out traffic spikes because queues act as a buffer against dudden burts of data.

# Core Concepts

**Producer** → Sends messages

**Queue** → Stores messages

**Consumer** → Processes messages

**Exchange** → Routes messages to queues

**Binding** → Rule connecting exchange to queue

**Routing Key** → Determines where message goes

# Types of Exchanges

RabbitMQ routes messages using exchanges:

Direct Exchange → Routes by exact match

Fanout Exchange → Broadcasts to all queues

Topic Exchange → Pattern-based routing (e.g., logs.\*)

Headers Exchange → Uses message headers

# What problem does RabbitMQ solve?

RabbitMQ solves the problem of reliable asynchronous communication between services by using queues to buffer and deliver messages safely.

# How does RabbitMQ ensure message reliability?

Message acknowledgments (ACKs) ensure messages are processed

Durable queues persist messages to disk

Publisher confirms ensure messages are delivered to the broker

# What is the difference between a queue and an exchange?

A queue stores messages

An exchange routes messages to queues based on rules (bindings and routing keys)

# What happens if a consumer crashes?

If a message is not acknowledged, RabbitMQ:

Re-queues the message

Sends it to another consumer

# What is a dead-letter queue?

A dead-letter queue (DLQ) stores messages that:

Failed processing

Expired

Were rejected

This helps with debugging and retry strategies.

# How does RabbitMQ handle load balancing?

RabbitMQ distributes messages across multiple consumers in a queue using a round-robin approach (or prefetch limits for fairness).

# What is message acknowledgment?

An acknowledgment (ACK) is sent by a consumer after processing a message.
If no ACK is received, the message can be retried.

# RabbitMQ vs Kafka?

Feature RabbitMQ Kafka
Model Queue-based Log-based streaming
Message retention Deleted after consumed Retained for time
Use case Task processing Event streaming
Ordering Per queue Per partition
Throughput Moderate Very high

👉 RabbitMQ = task queue
👉 Kafka = event streaming platform

# What is prefetch count?

Prefetch count limits how many messages a consumer can process at once.
This prevents one worker from being overloaded.

# When would you use RabbitMQ?

Use RabbitMQ when:

You need reliable task processing

You want fine control over message routing

You need guaranteed delivery and retries
