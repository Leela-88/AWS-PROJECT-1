# Hosting a static website on  Amazon S3

Amazon Simple Storage Service (Amazon S3) can be used to host static Websites without a need for a Web server (at an extremely low cost). S3 buckets can be used to host the HTML, CSS and JavaScript files for entire static websites.

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/59f5d2be-b377-4618-a4b2-9e9afac57f8e)

# Introduction 
Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance

Amazon S3 Store and protect any amount of data for a range of use cases, such as data lakes, websites, cloud-native applications, backups, archive, machine learning, and analytics.

Amazon Web Services offers a simple and cost-effective solution for hosting static websites using Amazon S3

Most websites are becoming static websites which means they run zero server side code and consist of only HTML, CSS and JavaScript. With no server side code to run, there is no reason to host them on a traditional server.

You can start by creating an Amazon S3 bucket, enabling the Amazon S3 Website hosting feature, and configuring access permissions for the bucket. After you have uploaded files and setup Website, Amazon S3 takes care of serving your content to your visitors.

Amazon Route 53: You can also use Amazon Route 53 (a managed Domain Name System (DNS) service) to point your domain to your Amazon S3 bucket.

Amazon CloudFront: You can also use Amazon CloudFront to enable your website to load quickly. Amazon CloudFront will create a content delivery network (CDN) that hosts your website content in close proximity to your users.


# Prerequisites

1.An AWS account (sign up at https://aws.amazon.com/ if you don’t have one)

2.website that which you want to host on Amazon S3

# Set-Up Instructions

Step 1 - Create an S3 bucket

1.Log in to your AWS Management Console and Navigate to the Amazon S3 service






![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/aa777a04-7204-4c56-b168-cb8d4128e5ec)


2.Click On “Create bucket” to begin creating a new bucket


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/f4d4f4ac-9f09-4a7b-a4de-993461b61868)


3.Provide a unique name for your bucket and choose the region closest to your target audience or your residence region


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/09223736-62ba-403b-8da0-af3528b1cc7b)


4.Uncheck ‘Block all public access’ to make all the objects Public in the bucket and Check the acknowledge box


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/3f45339b-9aae-42b4-a95e-5e477d83e08f)


5.Keep the default settings for the rest of the options and click On “Create” then a pop-up will appear stating that successfully created bucket 


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/3880ea17-3842-427d-9fbb-485277852d31)






 







