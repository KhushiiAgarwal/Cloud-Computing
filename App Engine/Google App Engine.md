

**Problem statement : Install Google App Engine. Create hello world app using Python**

Developers upload their apps to App Engine, and Google Cloud takes care of the rest. The notion of servers, virtual machines, and instances have been abstracted away, with App Engine providing all the compute necessary. Developers don't have to worry about operating systems, web servers, logging, monitoring, load-balancing, system administration, or scaling, as App Engine takes care of all that. Developers only need to focus on building solutions for their organizations or their users.

The App Engine standard environment provides application-hosting services supporting the following languages: Python, Java, PHP, Go, Node.js, and Ruby). The App Engine flexible environment provides even more flexibility by supporting custom runtime

1. **Enable Google App Engine Admin API**

Search App enginer admin API in search bar and enable it

` `![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.001.png)


1. **Download the Hello World app using Clone repository** 

Use the github repo or create a simple app: 

[https://github.com/GoogleCloudPlatform/python-docs- samples/tree/main/appengine/standard_python3/hello_world](https://github.com/GoogleCloudPlatform/python-docs-%20samples/tree/main/appengine/standard_python3/hello_world)

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.002.png)

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.003.png)


![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.004.png)

1. **Test the application** 

Test the application using the Google Cloud development server (dev\_appserver.py), which is included with the preinstalled App Engine SDK. Type *dev\_appserver.py app.yaml*  in terminal

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.005.png)

View the results by clicking the on URL provided  > Preview on port 8080. A new browser window:

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.006.png)

1. **Make changes** 

Terminal *nano main.py*


![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.007.png)

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.008.png)


Change "Hello World!" to "New Text".

Save the file with CTRL-S and exit with CTRL-X.

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.009.png)

Reload the window

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.010.png)

1. **Deploy your app**

gcloud app deploy![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.011.png)

Enter Y when prompted to confirm the details and begin the deployment of service.

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.012.png)

![](Aspose.Words.808dcaea-8780-4202-849a-bee0822cfce5.013.png)
