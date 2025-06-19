---
title: Transformation and Aggregation Queries
author: Alessandro Salucci
date: 19.06.2025
---

# Transformation and Aggregation Queries

The two most common queries are **transformation** and **aggregation** queries.

## Transformation queries

**Transformation queries** *(also called **filter expressions**)* **filter input** or **add/remove/modify** fields on each event. These include filter expressions like:

```sql
time:dayOfWeekName(field=@timestamp, as=the_day)
```

This uses the [`time:dayOfWeekName()`](https://library.humio.com/data-analysis/functions-time-dayofweekname.html) function to extract the day of the week from the timestamp for each event, format that value to return the name of the day of the week, then put that value in a field titled **`the day`**.

A subset of the available query functions are known as Transformation Functions, for example `regex()`, `in()` or `eval()`. Just like the examples above, they only **add/remove/modify** fields and never produce new (additional) events as output.

If a query consists solely of transformation expressions it is known as a filter query or a transformation query. This kind of query is required when connecting [`Views`](https://library.humio.com/training/training-fc-repositories.html#training-fc-repositories-views) with repositories.

## Aggregation queries

**Aggregation queries** are always function calls. These functions combine their input into a new structure, or emit new events into the output stream.

Queries become an `aggregation query` if they use at least one aggregate function, like:

- [`sum();`](https://library.humio.com/data-analysis/functions-sum.html)

- [`count();`](https://library.humio.com/data-analysis/functions-count.html)

- [`avg()`](https://library.humio.com/data-analysis/functions-avg.html)

For example, the query [`count()`](https://library.humio.com/data-analysis/functions-count.html) takes a stream of events as its input, and produces a single record containing a `_count` field.

Below are some examples:

```sql
loglevel = ERROR | timechart()
```

```sql
x := y * 2 | bucket(function=sum(x))
```