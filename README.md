## \<aws-app\>

The aws-app element is used for initializing and configuring your
connection to AWS.


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
