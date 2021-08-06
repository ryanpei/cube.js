---
title: AWS Athena
permalink: /config/databases/aws-athena
---

## Prerequisites

- An AWS account with a Data Catalog and IAM credentials

For AWS Athena, you'll need to specify the AWS access and secret keys with the
[access necessary to run Athena queries][aws-docs-athena-access], and the target
AWS region and [S3 output location][aws-docs-athena-query] where query results
are stored.

## Setup

### Manual

Add the following to a `.env` file in your Cube.js project:

```bash
CUBEJS_DB_TYPE=athena
CUBEJS_AWS_KEY=AKIA************
CUBEJS_AWS_SECRET=****************************************
CUBEJS_AWS_REGION=us-east-1
CUBEJS_AWS_S3_OUTPUT_LOCATION=s3://my-athena-output-bucket
```

## Environment Variables

| Environment Variable            | Description                                                       | Possible Values                        | Required |
| ------------------------------- | ----------------------------------------------------------------- | -------------------------------------- | :------: |
| `CUBEJS_AWS_KEY`                | The AWS Access Key ID to use for database connections             | A valid AWS Access Key ID              |    ✅    |
| `CUBEJS_AWS_SECRET`             | The AWS Secret Access Key to use for database connections         | A valid AWS Secret Access Key          |    ✅    |
| `CUBEJS_AWS_REGION`             | The AWS region of the Cube.js deployment                          | [A valid AWS region][aws-docs-regions] |    ✅    |
| `CUBEJS_AWS_S3_OUTPUT_LOCATION` | The S3 path to store query results made by the Cube.js deployment | A valid S3 path                        |    ❌    |

## SSL

Cube.js does not require any additional configuration to enable SSL as AWS
Athena connections are made over HTTPS.

[aws-docs-athena-access]:
  https://docs.aws.amazon.com/athena/latest/ug/access.html
[aws-docs-athena-query]:
  https://docs.aws.amazon.com/athena/latest/ug/querying.html
[aws-docs-regions]:
  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#concepts-available-regions
