Name : Khushi Agarwal

Roll no:-79

Division: TY-CS-B

**Problem statement Lab 5: AWS IAM**

- **Working**
- **Architecture**
- **Use cases**
- **Best Practices for authorization using IAM**
- **Authentication & Authorization with cloud IAM**

**What is IAM?**
Identity management, access controls, and governance are foundational security pillars for organizations of any size and type. As you migrate to and modernize on AWS, your security and IT teams can adopt modern cloud-native identity solutions and Zero Trust architectures to securely support hybrid workforce productivity, provide builders and customers access experiences with less friction, apply and audit permissions toward least privilege, and help meet stringent compliance mandates.


**Features of IAM**

- **Shared access to your AWS account :** Grant other people permission to administer and use resources in your AWS account without having to share your password or access key.

- **Granular permissions:** Grant different permissions to different people for different resources. For example, you might allow some users complete access. For other users, you can allow read-only access to just some S3 buckets, or permission to administer just some EC2 instances, or to access your billing information but nothing else.

- **Secure access to AWS resources for applications that run on Amazon EC2:** Use IAM features to securely provide credentials for applications that run on EC2 instances. These credentials provide permissions for your application to access other AWS resources

- **Multi-factor authentication (MFA):**  Add two-factor authentication to your account and to individual users for extra security. With MFA you or your users must provide not only a password or access key to work with your account, but also a code from a specially configured device. If you already use a FIDO security key with other services, and it has an AWS supported configuration, you can use WebAuthn for MFA security.

- **Identity federation:** Allow users who already have passwords elsewhere to get temporary access to your AWS account.

- **Eventually Consistent :** IAM achieves high availability by replicating data across multiple servers within Amazon's data centers around the world. If a request to change some data is successful, the change is committed and safely stored. However, the change must be replicated across IAM, which can take some time. Such changes include creating or updating users, groups, roles, or policies. 


- **Free to use:** AWS Identity and Access Management (IAM) and AWS Security Token Service (AWS STS) are features of your AWS account offered at no additional charge. You are charged only when you access other AWS services using your IAM users or AWS STS temporary security credentials. 

- **Identity information for assurance**

- **PCI DSS Compliance:** IAM supports the processing, storage, and transmission of credit card data by a merchant or service provider, and has been validated as being compliant with Payment Card Industry (PCI) Data Security Standard (DSS). For more information about PCI DSS, including how to request a copy of the AWS PCI Compliance Package

- **Integrated with many AWS services**


**Why use IAM?**

- AWS Identity Services help you securely manage identities, resources, and permissions at scale.
- ` `Have identity services for your workforce and customer-facing applications to get started quickly and manage access to your workloads and applications. 
- IAM can be used to manage and scale workload and workforce access securely supporting your agility and innovation in AWS. 
- Centrally manage workforce access to multiple AWS accounts and applications


**AWS IAM ARCHITECTURE**

![](Aspose.Words.aa4aeb2a-2851-491e-bb91-92cc1fd3cf89.001.png)![](Aspose.Words.aa4aeb2a-2851-491e-bb91-92cc1fd3cf89.002.png)

**Benefits of AWS IAM**

- **Connect your existing identity source to streamline accessing AWS:** Give your workforce single sign-on access and a consistent experience across AWS services. Use your chosen identity source and IAM Identity Center alongside your existing IAM roles and policies.

- **Efficiently manage workforce access to AWS applications:** Allow easier management and auditing of user access to AWS applications by making user and group information from your identity source available through IAM Identity Center. You can do this while maintaining your existing access configurations for AWS accounts.

- **Improve control and visibility of user access to data in AWS applications:** Give your data owners the ability to authorize and log data access by user. Enable the transfer of user identity context from your business intelligence tool to the AWS data services you use, while continuing to use your chosen identity source and other AWS access management configurations.

- **Manage workforce access to a multi-account AWS environment:** Manage access consistently across multiple AWS accounts, discover who has access to what, and provide your workforce with single sign-on authentication. Use IAM Identity Center with your existing identity source or create a new directory, and manage workforce access to part or all of your AWS environment.

![](Aspose.Words.aa4aeb2a-2851-491e-bb91-92cc1fd3cf89.003.png)

**Identity use cases**

- Customer identity and access management
- Interact and engage your customers from sign-up to sign-in across digital channels using industry standards. Apply security controls, integrate developer tools, use customer analytics, and balance privacy and ease of use for your customers. 
- Workforce identity and access management
- Manage employee, vendor, partner, and resource access to AWS services and applications. Grant your workforce and workloads the access only needed to organizational and cloud-based applications and data.


  **Authentication:** A principal must be authenticated using their credentials to send a request to AWS

  **Authorization:**  You must also be authorized (allowed) to complete your request. During authorization, AWS uses values from the request context to check for policies that apply to the request. It then uses the policies to determine whether to allow or deny the request. Most policies are stored in AWS as JSON documents and specify the permissions for principal entities. There are several types of policies that can affect whether a request is authorized. To provide your users with permissions to access the AWS resources in their own account, you need only identity-based policies. Resource-based policies are popular for granting cross-account access. The other policy types are advanced features and should be used carefully.

  AWS checks each policy that applies to the context of your request. If a single permissions policy includes a denied action, AWS denies the entire request and stops evaluating. This is called an explicit deny. Because requests are denied by default, AWS authorizes your request only if every part of your request is allowed by the applicable permissions policies. The evaluation logic for a request within a single account follows these general rules:

  By default, all requests are denied. (In general, requests made using the AWS account root user credentials for resources in the account are always allowed.)

  An explicit allow in any permissions policy (identity-based or resource-based) overrides this default.

  The existence of an Organizations SCP, IAM permissions boundary, or a session policy overrides the allow. If one or more of these policy types exists, they must all allow the request. Otherwise, it is implicitly denied.

  An explicit deny in any policy overrides any allows.

  To learn more about how all types of policies are evaluated, see Policy evaluation logic. If you need to make a request in a different account, a policy in the other account must allow you to access the resource and the IAM entity that you use to make the request must have an identity-based policy that allows the request.

  **Actions or operations**

  After your request has been authenticated and authorized, AWS approves the actions or operations in your request. Operations are defined by a service, and include things that you can do to a resource, such as viewing, creating, editing, and deleting that resource. For example, IAM supports approximately 40 actions for a user resource, including the following actions:

- CreateUser

- DeleteUser

- GetUser

- UpdateUser

To allow a principal to perform an operation, you must include the necessary actions in a policy that applies to the principal or the affected resource.
