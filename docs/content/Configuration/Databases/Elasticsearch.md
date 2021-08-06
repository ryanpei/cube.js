---
title: Elasticsearch
permalink: /config/databases/elasticsearch
---

<!-- prettier-ignore-start -->
[[info | ]]
| This is a community-maintained driver; if you think this guide needs
| improving, please send us a pull request.
<!-- prettier-ignore-end -->

## Prerequisites

To connect to an Elasticsearch database, use `CUBEJS_DB_URL` with the username
and password embedded in the URL, if required.

<!-- prettier-ignore-start -->
[[warning | ]]
| If you're not using Elastic Cloud, you **must** specify
| `CUBEJS_DB_ELASTIC_QUERY_FORMAT`.
<!-- prettier-ignore-end -->

## Setup

### Manual

For a self-hosted Elasticsearch instance, add the following to a `.env` file in
your Cube.js project:

```bash
CUBEJS_DB_TYPE=elasticsearch
CUBEJS_DB_URL=
CUBEJS_DB_ELASTIC_QUERY_FORMAT=json
```

For an Elasticsearch instanced hosted by Elastic.co, add the following to a
`.env` file in your Cube.js project:

```bash
CUBEJS_DB_TYPE=elasticsearch
CUBEJS_DB_URL=
CUBEJS_DB_ELASTIC_APIKEY_ID=
CUBEJS_DB_ELASTIC_APIKEY_KEY=
```

## Environment Variables

| Environment Variable             | Description                                                                                                                                                                              | Possible Values                        | Required |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- | :------: |
| `CUBEJS_DB_URL`                  | The URL for a database                                                                                                                                                                   | A valid database URL for Elasticsearch |    ✅    |
| `CUBEJS_DB_ELASTIC_QUERY_FORMAT` | By default, queries return data in JDBC format, but you can also return data in standard Elasticsearch JDBC, JSON, CSV, YAML or raw formats (only JSON and JDBC are currently supported) | `json`, `jdbc`                         |    ❌    |
| `CUBEJS_DB_ELASTIC_OPENDISTRO`   | If `true`, then use the Open Distro for Elasticsearch                                                                                                                                    | `true`, `false`                        |    ❌    |
| `CUBEJS_DB_ELASTIC_APIKEY_ID`    | [ID of the API key from elastic.co][elastic-docs-api-keys]                                                                                                                               | A valid Elastic.co API key ID          |    ❌    |
| `CUBEJS_DB_ELASTIC_APIKEY_KEY`   | [Value of the API key from elastic.co][elastic-docs-api-keys]                                                                                                                            | A valid Elastic.co API key value       |    ❌    |

## SSL

Cube.js does not require any additional configuration to enable SSL as
Elasticsearch connections are made over HTTPS.

[elastic-docs-api-keys]:
  https://www.elastic.co/guide/en/kibana/master/api-keys.html#create-api-key
