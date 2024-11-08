---
title: Transform Data
description: How to transform data with Matatika
permalink: /how-to-guides/transform-data
parent: How-To Guides
---

# {{page.title}}

*Time required: **15 minutes***

---

## Prerequisites
- [Setup your Development Environment]({{site.baseurl}}/how-to-guides/setup-your-development-environment)

---

## Introduction
A data transform is a layer of logic that transforms one set of data into another - this is typically the 'T' in [ELT](https://en.wikipedia.org/wiki/Extract,_load,_transform){:target="_blank"}. An example of a simple transform might be to calculate the total amount each customer has spent across all orders they have placed. Matatika uses [dbt](https://www.getdbt.com/){:target="_blank"} as a transformation tool, which operates on the concept of transforms-as-code, in the form of templated SQL files.

## Create a source
A dbt source is a definition of the "source" database schema. To define a source, create a YAML file (e.g. `my_source.yml`) under the `transforms/models` directory (refer to the [dbt docs](https://docs.getdbt.com/reference/source-properties){:target="_blank"} for more information):

{% raw %}
```yml
version: 2

sources:
  - name: my_source
    schema: "{{ env_var('DBT_SOURCE_SCHEMA') }}"
    tables:
      - name: customers
      - name: orders
```
{% endraw %}

## Create a model
A dbt model translates to a database table that is created and updated by dbt. To create a model for a workspace, first create a new SQL file (e.g. `my_model.sql`) under the `transforms/models` directory. Start writing SQL in this file to define transform logic, using [dbt Jinja functions](https://docs.getdbt.com/reference/dbt-jinja-functions){:target="_blank"} to inject dynamic behaviour:

{% raw %}
```sql
{{ config(materialized='table') }}

with customers as (
    select * from {{ source('my_source', 'customers') }}
),
orders as (
    select * from {{ source('my_source', 'orders') }}
),
"final" as (
  select
    c.id
    , c."name"
    , SUM(o.product_price * o.quantity) as total_spend
  from customers c
  join orders o on o.customer_id = c.id
  group by c.id, c."name"
  order by total_spend desc
)
select * from "final"
```
{% endraw %}

## Run your models
dbt models require the source tables to exist before they are run. If the data isn't already present, you need to [run your data import locally]({{site.baseurl}}/how-to-guides/import-data/running-your-data-import-locally).

```sh
# ensure dbt is installed
meltano install transformer dbt

# run dbt models
meltano invoke dbt run
```
> See [`dbt run` docs](https://docs.getdbt.com/reference/commands/run){:target="_blank"} for more information

When a [pipeline]({{site.baseurl}}/glossary#pipeline) with dbt is run in the Matatika platform, models in the project will be automatically run.

