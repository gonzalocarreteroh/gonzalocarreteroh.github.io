Reference: https://www.youtube.com/watch?v=QkdkLdMBuL0&t=56s

---
Direct communication between different services in a micro services architecture can become complex and result in high [[Coupling]].

##### Post Office Analogy
Let's consider the scenario of people sending letters to each other. Rather than writing letters and having to physically deliver them to the recipient (time consuming), you can just leave them at the post office and let them handle the communication. In this way, you can dedicate all your time to writing.

Now, some people want to send letters, others packages, documents, etc. The post office usually has a different queues to process each type of incoming delivery. Furthermore, for highly busy queues (e.g. packages), the post office can add more workers that handle packages targeted to Europe, others to Asia, and so on.

![[kafka1.png]]

### Kafka Overview
Apache Kafka is like a post office but for communications between different services in your system.

In our analogy, these would be the Kafka equivalents:

- Post Office - <span style="color:green">Broker</span>
- Queue - <span style="color:green">Topic</span>
- Letter - <span style="color:green">Event</span>
- EU vs US - <span style="color:green">Partition</span>

Services (<span style="color:green">producers</span>) can produce <span style="color:green">events</span> (e.g. letter) and publish them to <span style="color:green">topics</span> (e.g. letters queue). Other services (<span style="color:green">consumers</span>) who are interested in receiving events of some type <span style="color:green">subscribe</span> to topics. If a topic has many traffic, we can create logical <span style="color:green">partitions</span> (e.g. EU letters, US letters), so that many producers can publish to the same topic at the same time and more workers can process the events.

#### Brokers
A broker is a server. Having many is like having many post office locations (scale and fault tolerance). Brokers persist in disk the events they process (reproducibility, on demand consumption), and handle message distribution to consumers.
#### Partitions
A topic partition can be distributed in many brokers. Thus, each partition has a **leader broker** and multiple replicas

#### Consumer Groups
A service pod will identify itself with a group ID (e.g. "billing-team"). When you scale a service and many equivalent pods are created (creating a consumer group), Kafka nows which type are they because of the group ID. Kafka will automatically distribute topic partitions to point to different replicas in the same consumer group (load balancing). If a pod fails, Kafka redirects the topic partition to point to a different pod that is alive.

![[kafka2.svg|697]]


---
Extend Note:
- Kafka Streaming
- Raft Consensus
- Code
