[![Build Status](https://travis-ci.org/gjdenhertog/polymeraws.svg?branch=master)](https://travis-ci.org/gjdenhertog/polymeraws)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://beta.webcomponents.org/element/gjdenhertog/polymeraws)
[![Bower version](https://badge.fury.io/bo/polymeraws.svg)](https://badge.fury.io/bo/polymeraws)


## \<aws-app\>

The aws-app element is used for initializing and configuring your
connection to AWS.


## \<aws-dynamodb\>

The `aws-dynamodb` element is an easy way to interact with a AWS DynamoDB
database. as an object and expose it to the Polymer databinding system.

Example usage:

```html
<aws-app
    region="eu-west-1">
</aws-app>
<aws-dynamodb
    table-name="notes"
    data="{{data}}">
</aws-dynamodb>
```

This fetches the `data` object from the `notes` table in the DynamoDB
database and exposes it to the Polymer databinding system. Changes to
`data` will likewise be sent back and stored.


## \<aws-lambda\>

The `aws-lambda` element is an easy way to invoke a AWS Lambda function.

Example usage:

```html
<aws-app
    region="eu-west-1">
</aws-app>
<aws-lambda
    id="transformNotes"
    function-name="transformNotes"
    on-response="handleResponse">
</aws-lambda>
```

The `aws-app` element initializes `AWS` in `aws-lambda`.

JavaScript invoke calls can then be made to the `aws-lambda` object to invoke
the Lambda function.

```javascript
this.$.transformNotes.invoke();
```

## \<aws-s3\>

The `aws-s3` element is an easy way to get objects from an S3 bucket.

Example usage:

```html
<aws-app
    region="eu-west-1">
</aws-app>
<aws-s3
    id="noteObject"
    bucket="noteBucket"
    object-key="firstNote"
    content="{{s3Object}}">
</aws-s3>
```

The `aws-s3` element initializes `AWS` in `aws-s3`.

JavaScript getObject calls can then be made to the `aws-s3` object to retrieve
the object contents.

```javascript
this.$.noteObject.getData();
```

JavaScript putObject calls can then be made to the `aws-s3` object to upload an
object to the bucket.

```javascript
this.$.noteObject.putObject(file, key, contentType);
```
