# Integration Patterns:  
{#integration-patterns}

Batch & Message

These patterns describe how data is transferred between systems when working with **batches (collections of records)** versus **messages (single events/records)**.

Integration Patterns:

[1. Batch → Batch ](#batch-batch)

[2. Batch → Batches](#batch-batches)

[3. Batch → Message ](#_Toc222255689)

[4. Batches → Batch](#batches-batch)

[5. Batches → Message](#batches-message)

[6. Message → Batch](#message-batch)

[7. Message → Batches ](#message-batches)

[Processing Actions across all patterns](#processing-actions-across-all-patterns)


## Batch → Batch 

**Definition:**  
A single batch of data is transformed into another batch.  
**Example:**  
Daily CSV file imported, transformed, and exported as another CSV/Excel/XML.

**Typical operations:**

- Mapping: Transform fields

- Filtering: Remove unwanted records

- Sorting: Order records

- Enrichment: Add lookup values (e.g., customer info)

## Batch → Batches 

**Definition:**  
One batch is split into multiple outgoing batches.  
**Example:**  
A big dataset split into files per region, per customer group, or per entity type.

**Operations:**

- Filtering: Split based on criteria

- Collecting: Group subsets

- Mapping/enrichment still apply

[]{#_Toc222255689 .anchor}Batch → Message

**Definition:**  
A batch is processed record-by-record and emitted as individual messages.  
**Example:**  
A nightly file triggers events for each row into a message bus (e.g., Azure Service Bus/Kafka).

**Operations:**

- Mapping each row into a message format

- Filtering out unwanted records

- Enrichment per row

## Batches → Batch 

**Definition:**  
Multiple batches are combined into a single batch.  
**Example:**  
Daily incremental files merged into a monthly file.

**Operations:**

- Collecting/merging records

- Sorting combined dataset

- De-duplication

- Mapping

## Batches → Message 

**Definition:**  
Multiple input batches produce message-by-message output.  
**Example:**  
All weekly CSV deliveries generate events for each line.

**Operations:**

- Same as batch → message

- May require incremental tracking

- Deduplication across batches

## Message → Batch 

**Definition:**  
Multiple messages are collected until a batch is created.  
**Example:**  
Events stored and then exported as a file every hour or after N records.

**Operations:**

- Collecting messages until a trigger condition is met

- Sorting before writing

- Mapping message data to batch schema

## Message → Batches 

**Definition:**  
Messages are collected and split into multiple target batches.  
**Example:**  
Incoming orders streamed in real-time and grouped into separate files per region.

**Operations:**

- Filtering into groups

- Collecting per group

- Sorting

- Enrichment

## Processing Actions (across all patterns)

**Mapping**

Transform fields from source structure to target structure.  
E.g. rename, convert types, flatten structures.

**Enrichment**

Add data from other systems (master data, reference lists, lookups).

**Sorting**

Order records or messages.

**Filtering**

Include/exclude based on rules (status, date, category).

**Collecting**

Aggregate items together until criteria are met:
- Time window
- Record count
- Business trigger

