## Batch → Message

**Definition:**  
A batch is processed record-by-record and emitted as individual messages.  
**Example:**  
A nightly file triggers events for each row into a message bus (e.g., Azure Service Bus/Kafka).

**Operations:**

- Mapping each row into a message format

- Filtering out unwanted records

- Enrichment per row
