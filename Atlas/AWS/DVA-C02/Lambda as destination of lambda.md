---
dudas: false
tags:
aliases:
incorrecta: false
---
Pregunta: [Exam AWS Certified Developer - Associate DVA-C02 topic 1 question 53 discussion - ExamTopics](https://www.examtopics.com/discussions/amazon/view/103723-exam-aws-certified-developer-associate-dva-c02-topic-1/)
### Dudas
- [x] is *failed destination* 4 Lambda a thing??
	Sí: [[Lambda#^c7a378|ver nota]].
### Notas
- 
### Situación
[[Lambda]] 2 gen thumbnail based on original pics. sometimes returns time-out. second [[Lambda]] 2 handle time-out and resize itself.

A developer is using an AWS Lambda function to generate avatars for profile pictures that are uploaded to an Amazon [[Simple Storage Service|S3]] bucket. The Lambda function is automatically invoked for profile pictures that are saved under the /original/ S3 prefix. The developer notices that **some pictures cause the Lambda function to time out**. The developer wants to implement a ==fallback mechanism== by using another Lambda function that resizes the profile picture.  
Which solution will meet these requirements with the LEAST development effort?

- A. Set the image resize Lambda function as a destination of the avatar generator Lambda function for the events that fail processing.
- B. Create an Amazon [[Simple Queue Service]] (Amazon [[Simple Queue Service|SQS]]) queue. Set the [[Simple Queue Service|SQS]] queue as a destination with an on failure condition for the avatar generator Lambda function. Configure the image resize Lambda function to poll from the [[Simple Queue Service|SQS]] queue.
- C. Create an AWS Step Functions state machine that invokes the avatar generator Lambda function and uses the image resize Lambda function as a fallback. Create an Amazon EventBridge rule that matches events from the S3 bucket to invoke the state machine.
- D. Create an Amazon Simple Notification Service (Amazon SNS) topic. Set the SNS topic as a destination with an on failure condition for the avatar generator Lambda function. Subscribe the image resize Lambda function to the SNS topic.
### Condiciones
- least dev effort

### OPTS
a. 2nd lambda as target of 1st lambda -- es posible y requiere menos código que b y d ^b1c26a

b. [[SQS]] as 1st Lambda's target on failure. 2nd lambda polls from it.

c. [[Step Functions]]

d. [[SNS]] as target. On-failure triggers 2nd Lambda. ^cb4fe6

### Análisis
Para mí, es la [[Lambda as destination of lambda#^cb4fe6|D]].
> [!note] Mi respuesta
> 
### Answer
[[Lambda as destination of lambda#^b1c26a|A]].