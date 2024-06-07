Name : Khushi Agarwal

Roll no:-79

Division: TY-CS-B

**Problem statement Tut 6: Perform any 3**

- **AWS Autoscaling**
- **ELB types & 3 levels**
- **CloudWatch**
- **CloudTrail**
- **Lambda**


**AWS Autoscaling**

AWS Auto Scaling monitors your applications and automatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost. Using AWS Auto Scaling, it’s easy to setup application scaling for multiple resources across multiple services in minutes. The service provides a simple, powerful user interface that lets you build scaling plans for resources including Amazon EC2 instances and Spot Fleets, Amazon ECS tasks, Amazon DynamoDB tables and indexes, and Amazon Aurora Replicas. AWS Auto Scaling makes scaling simple with recommendations that allow you to optimize performance, costs, or balance between them. 

![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.001.png)

**Benefits**

- **Setup Scaling Quickly** : AWS Auto Scaling lets you set target utilization levels for multiple resources in a single, intuitive interface. You can quickly see the average utilization of all of your scalable resources without having to navigate to other consoles.

- **Make Smart Scaling Decisions**: AWS Auto Scaling lets you build scaling plans that automate how groups of different resources respond to changes in demand. You can optimize availability, costs, or a balance of both. AWS Auto Scaling automatically creates all of the scaling policies and sets targets for you based on your preference. AWS Auto Scaling monitors your application and automatically adds or removes capacity from your resource groups in real-time as demands change.

- **Automatically Maintain Performance:** Using AWS Auto Scaling, you maintain optimal application performance and availability, even when workloads are periodic, unpredictable, or continuously changing. AWS Auto Scaling continually monitors your applications to make sure that they are operating at your desired performance levels. When demand spikes, AWS Auto Scaling automatically increases the capacity of constrained resources so you maintain a high quality of service.

- **Pay Only For What You Need:**AWS Auto Scaling can help you optimize your utilization and cost efficiencies when consuming AWS services so you only pay for the resources you actually need. When demand drops, AWS Auto Scaling will automatically remove any excess resource capacity so you avoid overspending. AWS Auto Scaling is free to use, and allows you to optimize the costs of your AWS environment.


![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.002.png)

**Types of AWS Auto Scaling![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.003.png)**

1. **Reactive Scaling:** In Reactive auto-scaling, the resources are scaled in response to traffic surges. It conducts real-time monitoring of scalable resources. The instances are used based on the coming traffic.

1. **Predictive Scaling:**  Predictive auto-scaling uses machine learning to forecast the traffic. The algorithm takes in historical data from CloudWatch. It then calculates the required resource capacity. 

1. **Scheduled Scaling:** Scheduled scaling adjusts resources based on a schedule. It lets you add a schedule to manage capacity on certain days.


1. **Manual Scaling:** You can change the number of instances manually in this auto-scaling. It also lets you change the size of the Auto Scaling group.  You either update the Auto Scaling group or the instances. Manual scaling is used when you do not require automatic scaling.

1. **Dynamic Scaling:** Dynamic auto-scaling works on signals given by the CloudWatch alarm. The metrics that trigger the alarm are coming from the Auto Scaling group.

**AWS CloudTrail**

AWS CloudTrail is a service that enables governance, compliance, operational auditing, and auditing of your AWS account.

**Benefits**

**Aggregate and consolidate multisource events:** With CloudTrail Lake, you can ingest activity events from AWS and sources outside AWS, including other cloud providers, in-house applications, and SaaS applications running in the cloud or on premises.

- **Immutably store audit-worthy events:** In AWS CloudTrail Lake, you can immutably store audit-worthy events. Easily generate audit reports required by internal policies and external regulations.

- **Derive insights and analyze unusual activity:** Detect unauthorized access and analyze activity logs using SQL-based queries or Amazon Athena. Respond with rules-based EventBridge alerts and automated workflows.

**To create a CloudTrail trail with the AWS Management Console**

- Sign in to the AWS Management Console and open the CloudTrail console at https://console.aws.amazon.com/cloudtrail/.

- On the CloudTrail service home page, the Trails page, or the Trails section of the Dashboard page, choose Create trail.

- On the Create Trail page, for Trail name, type a name for your trail. For more information, see Naming requirements.

- If this is an AWS Organizations organization trail, you can enable the trail for all accounts in your organization. To see this option, you must sign in to the console with a user or role in the management or delegated administrator account. To successfully create an organization trail, be sure that the user or role has sufficient permissions. For more information, see Creating a trail for an organization.

- For Storage location, choose Create new S3 bucket to create a bucket. When you create a bucket, CloudTrail creates and applies the required bucket policies.

- For Log file SSE-KMS encryption, choose Enabled if you want to encrypt your log files using SSE-KMS encryption instead of SSE-S3 encryption. The default is Enabled.

- For Tags, add one or more custom tags (key-value pairs) to your trail. Tags can help you identify both your CloudTrail trails and the Amazon S3 buckets that contain CloudTrail log files. You can then use resource groups for your CloudTrail resources.

![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.004.png)


![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.005.png)

**AWS CloudWatch**

Amazon CloudWatch is a service that monitors applications, responds to performance changes, optimizes resource use, and provides insights into operational health. By collecting data across AWS resources, CloudWatch gives visibility into system-wide performance and allows users to set alarms, automatically react to changes, and gain a unified view of operational health.

![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.006.png)

**Benefits**

- **Visualize and analyze your data with end-to-end observability:** Collect, access, and analyze your resource and application data using powerful visualization tools

- **Operate efficiently with automation:** Improve operational performance using alarms and automated actions set to activate at predetermined thresholds

- **Quickly obtain an integrated view of your AWS or other resources:** Seamlessly integrate with more than 70 AWS services for simplified monitoring and scalability

- **Proactively monitor and get actional insights to enhance end user experiences:** Troubleshoot operational problems with actionable insights derived from logs and metrics in your CloudWatch dashboards

![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.007.png)

![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.008.png)

![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.009.png)

**AWS Lambda**

AWS Lambda is a compute service that runs your code in response to events and automatically manages the compute resources, making it the fastest way to turn an idea into a modern, production, serverless applications.

**Benefits** 

- **No need for managing servers:** Run code without provisioning or managing infrastructure. Simply write and upload code as a .zip file or container image.

- **Automatic scaling:** Automatically respond to code execution requests at any scale, from a dozen events per day to hundreds of thousands per second.

- **Pay-as-you-go pricing:** Save costs by paying only for the compute time you use—by the millisecond—instead of provisioning infrastructure upfront for peak capacity.

- **Performance optimization:** Optimize code execution time and performance with the right function memory size. Respond to high demand in double-digit milliseconds with Provisioned Concurrency.

- **Stream Processing![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.010.png)**


- **File Processing![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.011.png)**


- **Web Application![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.012.png)**


- **IoT ( Internet of Things) Backend**

  ![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.013.png)


- **Mobile Backend![](Aspose.Words.af97d713-2336-4985-aec9-178c09a0ee5a.014.png)**

