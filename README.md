
# Lambda function through ApiGateway and stores data in to DynamoDB.

### Description:
Trigger Lambda function through ApiGateway and stores data in to DynamoDB. You need to follow these below steps.

#### steps:
1. dynamodb.yaml
2. PostlambdaFunc.yaml
3. GetLambdaFunc.yaml
4. DeleteLambdaFunc.yaml
5. apiGatewayWithLambda.yaml

### dynamoDB Stack:
~~~
Upload dynamodb.yaml Stack.
~~~

**Description:**
This stack create dynamoDB table with name 'customers' and create IAM role with LambdaFullAccess and apiGatewayFullAccess.



### PostLambdaFunc.yaml Stack:
~~~
Upload PostLambdaFunc.yaml Stack.
~~~

**Description:**
This Stack create lambda which Get values form apiGateway and stores them in to dynamoDB which we created in above stack.



### GetLambdaFunc.yaml Stack:
~~~
Upload GetLambdaFunc.yaml Stack.
~~~

**Description:**
This Stack create lambda which Get Key values form apiGateway and get data from dynamoDB and pass them back to apiGateway.


### DeleteLambdaFunc.yaml:
~~~
Upload DeleteLambdaFunc.yaml Stack
~~~

**Description:**
This Stack create lambda which Get Key values form apiGateway and delete that data in to dynamoDB.


### apiGatewayWithLambda.yaml:
~~~
Upload apiGatewayWithLambda.yaml Stack
~~~

**Description:**
This stack create apiGateway with POST,GET,DELETE methods and connect them to lambda function. when we create any event in to apiGateway it pass event to their corresponding lambda function.


### Tips:
#### 1.
use this in to post method in apiGateway
~~~
{ "customersId":"Any Number","Name":"Any value","Location":"Any location" }
~~~

#### 2.
use this in to Delete method in apiGateway
~~~
{"customerId":"Any Number"}
~~~


#### 3.
use this in to Get method in apiGateway
~~~
{"customerId":"Any Number"}
~~~


