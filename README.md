[![Build Status](https://travis-ci.org/gjdenhertog/polymeraws.svg?branch=master)](https://travis-ci.org/gjdenhertog/polymeraws)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://beta.webcomponents.org/element/gjdenhertog/polymeraws)
[![Bower version](https://badge.fury.io/bo/polymeraws.svg)](https://badge.fury.io/bo/polymeraws)


## \<aws-app\>

`<aws-app>` initializes and configures your connection to AWS.
The app is permanently initialized once attached and should not be dynamically bound.

Example usage:

```html
<aws-app region="eu-west-1"></aws-app>
```

## \<aws-cognito\>

`<aws-cognito>` provides API wrapping and Polymer data binding for Amazon's
Cognito service.

Example usage:

```html
<aws-app region="us-east-1"></aws-app>
<aws-cognito id="cognito"
    user-pool-id="us-east-1_XXXXXXXXX"
    client-id="3XXXXXfea3nXXX0k3XXXXXX9p5"
    identity-pool-id="us-east-1:XXXXXXXX-XXXX-XXXX-XXXX-XXXXAXXXXXXX"
></aws-cognito>
```

## \<aws-dynamodb\>

`<aws-dynamodb>` provides an easy way to retrieve and update AWS DynamoDB data.

Example usage:

```html
<aws-app region="eu-west-1"></aws-app>
<aws-dynamodb
    table-name="notes"
    data="{{data}}"
></aws-dynamodb>
```

This fetches the `data` object from the `notes` table in the DynamoDB database
and exposes it to the Polymer data binding system. Changes to `data` are
likewise sent back and stored.

## \<aws-lambda\>

`<aws-lambda>` provides an easy way to invoke a AWS Lambda function.

Example usage:

```html
<aws-app region="eu-west-1"></aws-app>
<aws-lambda id="transformNotes"
    function-name="transformNotes"
    on-response="handleResponse"
></aws-lambda>
```
