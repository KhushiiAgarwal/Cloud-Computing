

**Problem statement Lab 4: To create AWS account and use S3 storage bucket**

Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance. It allows to store and protect any amount of data for a range of use cases, such as data lakes, websites, cloud-native applications, backups, archive, machine learning, and analytics for upto 12 months free. Its standard features include:

- 5 GB in the S3 Standard storage class

- 20,000 Get Requests

- 2,000 Put, Copy, Post, or List Requests

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.001.png)

1\.**Create a bucket**

1. Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/.
1. In the left navigation pane, choose Buckets.
1. Choose Create bucket.
1. The Create bucket page opens.
1. For Bucket name, enter a unique name for your bucket (following the naming convention).
1. After you create the bucket, you cannot change its name.	

   ![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.002.png)

To create a bucket a region is selected and unique name is provided. We can also use existing bucket configuration using choose bucket button

**Bucket naming convention**: The bucket name must:

1. Be unique within a partition. A partition is a grouping of Regions. AWS currently has three partitions: aws (Standard Regions), aws-cn (China Regions), and aws-us-gov (AWS GovCloud (US) Regions).
1. Be between 3 and 63 characters long.
1. Consist only of lowercase letters, numbers, dots (.), and hyphens (-). Avoid using dots (.) in bucket names, except for buckets that are used only for static website hosting.
1. Begin and end with a letter or number.

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.003.png)

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.004.png)

![ref1]


1. **Upload a file in a bucket:** To upload an object to a bucket
   1. Open the Amazon S3 console at https://console.aws.amazon.com/s3/.
   1. In the Buckets list, choose the name of the bucket that you want to upload your object to.
   1. On the Objects tab for your bucket, choose Upload.
   1. Under Files and folders, choose Add files.
   1. Choose a file to upload, and then choose Open.
   1. Choose Upload.

![ref2]

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.007.png)

Click on bucket name & select objects tab to upload a new file.

Selecting the new file, the destination of storage folder is also displayed

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.008.png)

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.009.png)

The size & properties of file is displayed after successful upload. 

It further reflects in object dashboard.

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.010.png)

If you want to choose which objects you delete without emptying all the objects from your bucket, you can delete an object.

- In the Buckets list, choose the name of the bucket that you want to delete an object from.

- Select the object that you want to delete.

- Choose Delete from the options in the upper right.

- On the Delete objects page, type delete to confirm deletion of your objects.

- Choose Delete objects.

If you plan to delete your bucket, you must first empty your bucket, which deletes all the objects in the bucket.

To empty a bucket

- In the Buckets list, select the bucket that you want to empty, and then choose Empty.

- To confirm that you want to empty the bucket and delete all the objects in it, in Empty bucket, type permanently delete.

After you empty your bucket or delete all the objects from your bucket, you can delete your bucket.

- To delete a bucket, in the Buckets list, select the bucket.

- Choose Delete.

- To confirm deletion, in Delete bucket, type the name of the bucket.

- To delete your bucket, choose Delete bucket.

![](Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.011.png)

[ref1]: Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.005.png
[ref2]: Aspose.Words.d46b367a-0e02-4ab1-9daa-defef9b67fca.006.png
