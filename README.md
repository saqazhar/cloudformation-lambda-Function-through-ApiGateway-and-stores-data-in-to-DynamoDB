
# Lambda function through ApiGateway and stores data in to DynamoDB.

### Description:
Trigger Lambda function through ApiGateway and stores data in to DynamoDB.

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
This stack create VPC with 2 Public Subnets and 1 Private Subnet. The private subnet can access the Internet by using a network address translation (NAT) gateway that resides in the public subnet. All Subnets are in Different Availability zones with their CIRDBlocks { (10.0.0.0/24)Subnet1, (10.0.2.0/24)Subnet2, (10.0.1.0/24)Subnet3 }. Then we have a Security Group. 1 for Load balancer 1 for PublicInstances 1 for Private Instance that we use in Other Stack. Then we have Output part that export values of Resources to use in other Stacks.



### GetLambdaFunc.yaml Stack:
~~~
Upload GetLambdaFunc.yaml Stack.
~~~

**Description:**
Instance Stack create Private Instance in Private Subnet with Security Group. Its in Private Subnet so they have internet access through the public Subnet.



### DeleteLambdaFunc.yaml:
~~~
Upload DeleteLambdaFunc.yaml Stack
~~~

**Description:**
In this stack we have AutoScalingGroup with LaunchConfiguration file. AutoScalingGroup create public instances in public subnets and private instance in private subnet as per thier availability zones. Then we have Load Balancer which balance load between instances.



### apiGatewayWithLambda.yaml:
~~~
Upload apiGatewayWithLambda.yaml Stack
~~~

**Description:**
In this stack we have AutoScalingGroup with LaunchConfiguration file. AutoScalingGroup create public instances in public subnets and private instance in private subnet as per thier availability zones. Then we have Load Balancer which balance load between instances.
