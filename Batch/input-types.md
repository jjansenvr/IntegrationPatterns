# most common batch-event file types
If you want only the most standard and widely used, here they are:

- CSV
- Fixed Length / Fixed Width
- XML (with multiple message elements)
- JSON Array
- JSONL / NDJSON
- EDI (EDIFACT, X12)

## Delimited text formats (line based)
These store many records line by line and might have a header line with names and other lines with values 
- CSV – Comma-Separated Values
- TSV – Tab-Separated Values
- PSV – Pipe-Separated Values (|)
- DSV – Generic Delimiter-Separated Values

## Fixed-width formats (line based)
Each record uses fixed character positions.
- Fixed Length / Fixed Width 

## Line-delimited structured formats
Each line is its own message.
- JSON Lines / JSONL / NDJSON (.jsonl, .ndjson)
- XML Lines (less common but possible)

## Hierarchical message batch formats

### XML-based
- XML Batch file (custom schemas like <Batch> enclosing multiple <Message> elements)
- XBRL, UBL, SOAP batch envelopes

### JSON-based
- JSON array (e.g. [{...}, {...}, ...])
- Bulk API formats (Elasticsearch bulk JSON, etc.)

## EDI formats (Electronic Data Interchange)
Often multine fixed length files 
These always contain batches of structured transactions/messages.

- EDIFACT (.edi, .edifact)
- X12 (.x12)

## Log/stream export batch formats
Logs often represent a batch of events.

- Log files (.log, .txt) – line-per-event
- Apache Parquet (.parquet) – columnar, big batches
- Apache Avro (.avro) – compact binary batch record format
- Apache ORC (.orc) – big-data optimized

