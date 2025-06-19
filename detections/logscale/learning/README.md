# 🦅 CrowdStrike Query Language Defined

`CrowdStrike Query Language (CQL)` is the query syntax to use when composing queries to retrieve, process and analyze data in **Falcon LogScale**. Built around a chain of data-processing commands linked together, each expression passes its result to the next expression in the sequence, allowing you to create complex queries by combining expressions. This architecture is similar to **command pipes in Unix and Linux shells**.

Events ingested and parsed in LogScale can be any type of text based data, can be both structured and unstructured, and can originate anywhere from application logs and infrastructure events to networks, security-related devices, or applications.

Much like a query for an SQL database, `CQL` **queries are written to include or exclude values** from a repository or view. However, unlike most SQL queries, **you can also do calculations** and **transform data**.

---

## 📚 Table of Content

- 📄 [01 Transformation and Aggregation Queries](./01-Transformation-and-Aggregation-Queries.md)
- 📄 [02 LogScale Query Language Syntax](./02-LogScale-Query-Language-Syntax.md)