---
title: Databricks JDBC
permalink: /config/databases/jdbc/databricks
---

## Prerequisites

Starting from `v0.26.83`, Cube.js provides a driver for Databricks. It's based
on the JDBC driver from Databricks, which requires [installation of Java with
JDK][gh-cubejs-jdbc-install].

## Setup

### Manual

Add the following to a `.env` file in your Cube.js project:

```dotenv
CUBEJS_DB_TYPE=databricks-jdbc
# CUBEJS_DB_NAME is optional
CUBEJS_DB_NAME=default
# You can find this inside the cluster's configuration
CUBEJS_DB_DATABRICKS_URL=jdbc:spark://dbc-XXXXXXX-XXXX.cloud.databricks.com:443/default;transportMode=http;ssl=1;httpPath=sql/protocolv1/o/XXXXX/XXXXX;AuthMech=3;UID=token;PWD=XXXXX
```

## Environment Variables

| Environment Variable       | Description                            | Possible Values       | Required |
| -------------------------- | -------------------------------------- | --------------------- | :------: |
| `CUBEJS_DB_NAME`           | The name of the database to connect to | A valid database name |    ✅    |
| `CUBEJS_DB_DATABRICKS_URL` | The URL for a JDBC connection          | A valid JDBC URL      |    ✅    |

[gh-cubejs-jdbc-install]:
  https://github.com/cube-js/cube.js/blob/master/packages/cubejs-jdbc-driver/README.md#java-installation
[ref-env-var]: /reference/environment-variables#database-connection
