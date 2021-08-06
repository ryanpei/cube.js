---
title: Druid
permalink: /config/databases/druid
---

## Prerequisites

## Setup

### Manual

Add the following to a `.env` file in your Cube.js project:

```bash
CUBEJS_DB_TYPE=druid
CUBEJS_DB_URL=https://my.druid.database
CUBEJS_DB_USER=druid
CUBEJS_DB_PASS=**********
```

## Environment Variables

| Environment Variable | Description                                                             | Possible Values                | Required |
| -------------------- | ----------------------------------------------------------------------- | ------------------------------ | :------: |
| `CUBEJS_DB_URL`      | The URL for a database                                                  | A valid database URL for Druid |    ✅    |
| `CUBEJS_DB_USER`     | The username used to connect to the database                            | A valid database username      |    ✅    |
| `CUBEJS_DB_PASS`     | The password used to connect to the database                            | A valid database password      |    ✅    |
| `CUBEJS_DB_SSL`      | If `true`, enables SSL encryption for database connections from Cube.js | `true`, `false`                |    ❌    |

## SSL

Cube.js does not require any additional configuration to enable SSL as Druid
connections are made over HTTPS.
