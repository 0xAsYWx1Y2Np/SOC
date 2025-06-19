---
title: LogScale Query Language Syntax
author: Alessandro Salucci
date: 19.06.2025
---

# LogScale Query Language Syntax

The `CrowdStrike Query Language (CQL)` is the syntax that lets you compose queries to retrieve, process, and analyze data in Falcon LogScale.

The query language is built around a chain of data-processing commands linked together. Each expression passes its result to the next expression in the sequence, allowing you to create complex queries by combining query expressions. This architecture is similar to [**command pipes**](https://en.wikipedia.org/wiki/Pipeline_(Unix)), a powerful and flexible mechanism for advanced data analysis in Unix and Linux shells.

This reference section on the CrowdStrike Query Language provides detailed explanations on several related topics. They are listed in the following with brief descriptions:

---

## Comments

Adding comments to query syntax is a great way to facilitate knowledge transfer and make query triage much easier. The CrowdStrike Query Language (CQL) supports `// single-line` and `/* multi-line */` comments.

```java
// This is a single line comment
#event_SimpleName = ProcessRollup2
```

```java
/* This is a 
   multi line comment
   to explain whats happening. */
#event_SimpleName = ProcessRollup2
```

---

## Query Filters

When querying data in LogScale, filters may be used to reduce the results to the relevant data. You can use free-text filters to grep data, or you can filter based on fields, stipulating acceptable field values or using regular expressions for matching field contents.

```sql
src="client" AND ip="127.0.0.1"
```