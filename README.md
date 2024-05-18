AMAZON ELASTIC BEANSTALK

To create an Elastic Beanstalk environment in AWS from scratch, I first sign in to my AWS Management Console at aws.amazon.com. Then, I navigate to the Services menu and select "Elastic Beanstalk" under the Compute section. Once there, I click on the "Create Application" button and provide a name for my application, optionally adding a description. After clicking "Create," I proceed to create a new environment by clicking "Create a new environment." Depending on the application's requirements, I select the environment tier, choosing either "Web server environment" for web applications or "Worker environment" for background processing, and then click "Select." This initiates the setup process for my Elastic Beanstalk environment, allowing me to configure and deploy my application with ease.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/4525a5e7-802b-413b-9b17-d85face0eed4)


Configure environment:

Click on the webserver environment to run our application in a webserver. 
After that we have to create an application, click on “create application” and give the Name for the application. Here I named it as Nodejs

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/c3b57e36-b147-4199-a6ca-293397df7dda)


And create an environment and configure it with suitable information to create an application 

![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/09c46676-661a-4309-b128-6e5ab9ca7d7c)
 

Next give the Platform type as Node.js to run the application in this Platform. And give the latest version and Branch.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/739946c4-babc-4651-9456-5061bf5da2d6)


Next, we can upload our code to run the application in Application code info, here gave it as sample application as default. In Presets I selected default Free tier Single instance as shown below. After that click on next.

![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/74501ba3-6f30-486f-993f-07458cf5a415)
 

Configure service access:
In service access configuration click on Create and use new service role in service role if  role has to create newly , but I had given the existing role I have , and an existing keypair to connect to the Server or instance atlast Ec2 instance profile as a role which attached to a Ec2 instance or S3 as shown in the below screenshot. Click on next.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/fb22b763-5e8a-47ac-8433-5983724074f8)


Virtual Private Cloud (VPC):
Next, we have to give the VPC configuration. Here I gave the default VPC to my Application. Click on the Instance Settings.

![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/f435ed6d-4ff6-429a-bff0-b36c2f34d191)
 

In Public Ip Address always tick on Activated it will assign a Public IP to the server and tick all availability Zones of subnets to the Instance as shown below. 
After that I left the remaining configurations as default, And click on next bottom.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/ed28aef1-4bae-4b84-b8e0-08a01f1c234c)


Configure instance traffic and scaling:
In instance root volume I had given my resources as shown below screenshot.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/8677c846-1831-4319-9134-14b4146c1ac8)


In Ec2 Security Groups I had given my existing Security Group I created in past as shown in the figure

![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/f5402651-568a-4428-bf9b-60cb9dcc1287)

 
Auto scaling group:
In Auto scaling group I gave Load balancer as the Environment Type with min and max of 1 instance as shown below. 

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/228f3622-2ff6-4cb5-9f97-8096aeba7bd3)


Give instance type as t2.micro for a free tier account, and left the remaining configurations as default. And give the Load balancer settings as below. And click on Next.

![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/e443581f-ea1e-4e26-999d-a4f0994fd435)

 
 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/d677a741-8d9e-4245-b855-364b019b281b)


Next, I didn’t change the default configuration of Monitoring, Managed platform updates and Rolling updates and deployments.
Platform software:  Give proxy server as Nginx as shown below. Click on Next.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/8beb4c0f-d5e4-472d-84e3-fdb346582807)


At last it show the all configuration of our Elastic Beanstalk to review the information given
 
 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/6c053548-c1d4-4ac2-a628-aae70501f70f)

![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/fc84e60e-9aff-436b-b565-35821e4fdc16)


After reviewing the details click on submit button, it will create an Elastic beanstalk with given configuration.
 
![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/0c5a35df-5c7e-4db5-af6a-445550266b07)

We Can check the event while creating the EBS as shown in the below screenshot. After processing is successfully complete it will create a Ec2 instance with Auto scaling.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/9c4538f1-1c21-457c-a5d8-175f5ba5d443)


Finally, it was created after a few minutes, it has created an Ec2 Instance in which our application was running

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/37e7ddb6-3e18-4c3f-8ff7-692ab2882d4f)


After clicking on the Domain that created as default , it will shown the web application that was running a sample application in webserver as shown below.
 
![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/e4512313-925e-4207-b67e-b757cd99a192)
 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/e86969ee-5ae6-4f00-8722-c6fbca5bf43e)


We can see the Monitoring tab that shows the Application activities every 5 mins, as shown below.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/d8e04ea5-0210-4ab0-82e7-97494926752a)


At last, I successfully configured and deployed a fault-tolerant and high-availability Node.js application using Elastic Beanstalk in AWS. I followed the steps provided, giving my application a name, selecting Node.js as the platform, and choosing to launch it as multiple instances with a load balancer for enhanced reliability. Despite not selecting the Free Tier option, I ensured high availability by opting for the High Availability setting.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/b3f98613-2d95-4814-b509-86b9b1ad4848)


 After creating the application, I verified its status by checking the endpoint URL and reviewing the resources in the EC2 service, including the instances and load balancers. Everything appeared to be functioning smoothly without errors, as indicated by the green checkmarks and the absence of any issues in the environment. Lastly, I cleaned up the resources by deleting the application to avoid unnecessary costs. Overall, the deployment process was successful, and I now have a fault-tolerant and high-availability environment ready to host my Node.js application.

 ![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/146c891b-23a7-4604-b20c-4bfe5025371d)

And one Instance with Auto scaling and Load balancing is Running successfully as shown below.
 


![image](https://github.com/sainakka5/Creating_Elastic_Beanstalk_with_Sample_code/assets/136338958/3f559661-6d10-442d-ad59-b22f94ea80e7)










