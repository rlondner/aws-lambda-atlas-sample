# AWS Lambda-MongoDB Atlas example

This repository is an example of a very simple Lambda function creating a document into a MongoDB Atlas database.

## Setup instructions

Please refer to [this tutorial](https://www.mongodb.com/blog/post/serverless-development-with-nodejs-aws-lambda-mongodb-atlas) for complete setup instructions.

Note: I included the [zip.sh](https://github.com/raphaellondner-mongodb/lambda-atlas-create-doc/blob/master/zip.sh) script I use to easily create the archive.zip file to be uploaded to AWS Lambda.

## Test instructions

We recommend you use the [lambda-local NPM package](https://www.npmjs.com/package/lambda-local) to test your Lambda function locally with your Atlas cluster.

The [ll.sh](https://github.com/rlondner/aws-lambda-atlas-sample/blob/master/ll.sh) script allows you to easily run tests by configuring the following parameters:

```
ATLAS_USERNAME="<username>"
ATLAS_PASSWORD="<password>"
ATLAS_CLUSTER_NAME="<cluster_name>"
ATLAS_CLUSTER_SUFFIX="<cluster_suffix>"
```

with those parameters feeding into the following connection string format:

```
mongodb://$ATLAS_USERNAME:$ATLAS_PASSWORD@$ATLAS_CLUSTER_NAME-shard-00-00-$ATLAS_CLUSTER_SUFFIX.mongodb.net:27017,$ATLAS_CLUSTER_NAME-shard-00-01-$ATLAS_CLUSTER_SUFFIX.mongodb.net:27017,$ATLAS_CLUSTER_NAME-shard-00-02-$ATLAS_CLUSTER_SUFFIX.mongodb.net:27017/travel?ssl=true&replicaSet=$ATLAS_CLUSTER_NAME-shard-0&authSource=admin
```
