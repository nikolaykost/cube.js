---
title: Connecting from Tableau
permalink: /config/downstream/tableau
---

<InfoBox>
  <b>The SQL API and Extended Support for BI Tools</b> workshop on June 22, 2022.<br/> 
  You'll have the opportunity to learn the latest on Cube's <a href="https://cube.dev/blog/expanded-bi-support/">SQL API.</a><br /> 
  Check out the agenda and resigter for the workshop today on the <a href="https://cube.dev/events/sql-api">event page</a> 👈
</InfoBox>

You can connect to Cube from Tableau, a visual analytics platform, using the [Cube SQL
API][ref-sql-api].

## Enable Cube SQL API

<InfoBox>

Don't have a Cube project yet? [Learn how to get started
here][ref-getting-started].

</InfoBox>

### Cube Cloud

Click **How to connect your BI tool** link on the Overview page, navigate to the SQL API tab
and enable it. Once enabled, you should see the screen like the one below with
your connection credentials:

<div style="text-align: center">
  <img
    src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/cube-sql-api-modal.png"
    style="border: none"
    width="80%"
  />
</div>

### Self-hosted Cube

You need to set the following environment variables to enable the Cube SQL API.
These credentials will be required to connect to Cube from Apache Superset
later.

```dotenv
CUBEJS_PG_SQL_PORT=5432
CUBE_SQL_USERNAME=myusername
CUBE_SQL_PASSWORD=mypassword
```

## Connecting from Tableau

Tableau connects to Cube as to a Postgres database.

In Tableau, select PostgreSQL connector and enter credentials from the above
step.

![adding Cube to Tableau as a SQL data source][ref-connecting-from-tableau]

## Querying data

Your cubes will be exposed as tables, where both your measures and dimensions are columns.

![Cube data in Tableau][ref-querying-from-tableau]

[ref-getting-started]: /cloud/getting-started
[ref-sql-api]: /backend/sql

[ref-connecting-from-tableau]: https://cubedev-blog-images.s3.us-east-2.amazonaws.com/dc025b24-674f-4f32-ac44-421d546ee676.GIF
[ref-querying-from-tableau]: https://cubedev-blog-images.s3.us-east-2.amazonaws.com/ea73a998-e2ce-4814-863e-425b4d35860c.gif
