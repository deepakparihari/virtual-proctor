# virtual-proctorirtual Proctor using Amazon Rekognition
Proctoring is the act of supervising an exam or course online.

Using web-based applications, virtual proctoring platforms allow test takers to be virtually monitored by a human via the webcam on their computer. To increase the scale of the test taking and improve a human proctor’s ability to monitor students, virtual proctoring services are now implementing AI/ML to support the human proctor.

Virtual Proctor is a solution that leverages Amazon Rekognition to show a scalable way to conduct online testing.

It shows how you can implement rules such as:

Detecting objects of interest (such as mobile phone)
Detecting the number of people present
Recognizing the person who is taking a test
Detecting unsafe content (such as explicit adult content or violent content)
You can also use Amazon Rekognition Custom Labels to detect other custom objects of interest.

Index
Architecture
Usage
Prerequisites
Deployment
Accessing the application
Remove the application
Making changes to the code and customization
[Samples]
Contributing
Architecture
Architecture Diagram

Usage
Prerequisites
To deploy the sample application, you will require an AWS account. If you don’t already have an AWS account, create one at https://aws.amazon.com by following the on-screen instructions. Your access to the AWS account must have IAM permissions to launch AWS CloudFormation templates that create IAM roles.

To use the sample application you will require a modern browser and a webcam.

Deployment
The demo application is deployed as an AWS CloudFormation template.

Note
You are responsible for the cost of the AWS services used while running this sample deployment. There is no additional cost for using this sample. For full details, see the following pricing pages for each AWS service you will be using in this sample. Prices are subject to change.

Amazon Rekognition Pricing
Amazon S3 Pricing
Amazon Cognito Pricing
Amazon CloudFront Pricing
Deploy the latest CloudFormation template by following the link below for your preferred AWS region:
Region	Launch Template
US East (N. Virginia) (us-east-1)	Launch the VirtualProctor Stack with CloudFormation
US East (Ohio) (us-east-2)	Launch the VirtualProctor Stack with CloudFormation
US West (Oregon) (us-west-2)	Launch the VirtualProctor Stack with CloudFormation
EU (Ireland) (eu-west-1)	Launch the VirtualProctor Stack with CloudFormation
Asia Pacific (Sydney) (ap-southeast-2)	Launch the VirtualProctor Stack with CloudFormation
Asia Pacific (Singapore) (ap-southeast-1)	Launch the VirtualProctor Stack with CloudFormation
Asia Pacific (Mumbai) (ap-south-1)	Launch the VirtualProctor Stack with CloudFormation
If prompted, login using your AWS account credentials.

You should see a screen titled "Create Stack" at the "Specify template" step. The fields specifying the CloudFormation template are pre-populated. Click the Next button at the bottom of the page.

On the "Specify stack details" screen you may customize the following parameters of the CloudFormation stack:

Stack Name: (Default: VirtualProctor) This is the name that is used to refer to this stack in CloudFormation once deployed.
AdminEmail: The email address you wish to setup as the initial user of this Amazon Rekognition Virtual Proctor deployment.
MinConfidence: (Default: 85) Specifies the minimum confidence level for the labels to return.
ObjectsOfInterestLabels (Default "Mobile Phone,Cell Phone"): Comma-delimited list of labels used to detect Objects of interest.
CreateCloudFrontDistribution (Default: true) Creates a CloudFront distribution for accessing the web interface of the solution.
ResourcePrefix: (Default: VirtualProctor) Resource prefix to apply to resource names when creating statically named resources.
When completed, click Next

Configure stack options if desired, then click Next.

On the review you screen, you must check the boxes for:

"I acknowledge that AWS CloudFormation might create IAM resources"
"I acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND"
These are required to allow CloudFormation to create a Role to allow access to resources needed by the stack and name the resources in a dynamic way.

Click Create Change Set

On the Change Set screen, click Execute to launch your stack.

You may need to wait for the Execution status of the change set to become "AVAILABLE" before the "Execute" button becomes available.
Wait for the CloudFormation stack to launch. Completion is indicated when the "Stack status" is "CREATE_COMPLETE".

You can monitor the stack creation progress in the "Events" tab.
Note the url displayed in the Outputs tab for the stack. This is used to access the application.

Accessing the Application
The application is accessed using a web browser. The address is the url output from the CloudFormation stack created during the Deployment steps.

When accessing the application for the first time, you need to use the Admin e-mail provided during Stack Creation as the username. A temporary password will be sent to the same e-mail address. After authentication, it will be necessary to create a new password and click "Change".

To manage users, you can use the Cognito Users Pool console.

Remove the application
To remove the application open the AWS CloudFormation Console, click the Virtual Proctor project, right-click and select "Delete Stack". Your stack will take some time to be deleted. You can track its progress in the "Events" tab. When it is done, the status will change from "DELETE_IN_PROGRESS" to "DELETE_COMPLETE". It will then disappear from the list.

Making changes to the code and customization
The contributing guidelines contains some instructions about how to run the front-end locally and make changes to the back-end stack.

Samples
Python Samples contains python snippets for virtual proctoring usecases

Contributing
Contributions are more than welcome. Please read the code of conduct and the contributing guidelines.

License Summary
This library is licensed under the MIT-0 License. See the LICENSE file.
