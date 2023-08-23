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

## Step 1 - CREATE AN S3 BUCKET

### 1.Log in to your AWS Management Console and Navigate to the Amazon S3 service






![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/aa777a04-7204-4c56-b168-cb8d4128e5ec)


### 2.Click On “Create bucket” to begin creating a new bucket


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/f4d4f4ac-9f09-4a7b-a4de-993461b61868)


### 3.Provide a unique name for your bucket and choose the region closest to your target audience or your residence region


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/09223736-62ba-403b-8da0-af3528b1cc7b)


### 4.Uncheck ‘Block all public access’ to make all the objects Public in the bucket and Check the acknowledge box


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/3f45339b-9aae-42b4-a95e-5e477d83e08f)


### 5.Keep the default settings for the rest of the options and click On “Create” then a pop-up will appear stating that successfully created bucket 


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/3880ea17-3842-427d-9fbb-485277852d31)

## Step 2- ENABLE STATIC WEBSITE HOSTING

### 1.Once your bucket is created, select it from the list and go to the “Properties” tab

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/acc8a3e6-ef60-42ce-a5a2-295bc46c6bde)

### 2.Scroll down to the “Static website hosting” section and click “Edit.”

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/6e514ede-ea6e-4a1e-a9f6-8b4ab6c45baf)


### 3.Select “Enable” for the “Static website hosting” option and Enter the name of your default HTML file which you are going to use for
hosting(e.g. “index.html”).

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/ca4304d3-ca60-406a-9a8e-43364ff7e62b)

### 4.Here you can also give the Error document that is returned when an error occurs  and Click On “Save” to save the changes

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/10342ae5-c20d-4e23-8ab9-9d664fd1036f)


### 5.Now we can see that Static website hosting is Enabled,Now copy the bucket website endpoint.

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/8f89b870-bdcb-4b28-adb2-91d166738719)

## Step 3- UPLOAD THE WEBSITE CONTENT

### 1.In the bucket properties, navigate to the “Object” tab

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/2c294065-332f-47ee-9afa-b1d0781085ed)


### 2.Click “Add Files” to upload your website files to the bucket and Click ‘Upload’

### For Example: You can use sample Website "Website" folder contents (provided in this repository).

### index.html
### error.html
### images[1.jpg]

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/72e97a31-9a95-4f3d-9abc-fb87a6eb97a7)


![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/75d4267d-dc58-4057-bccd-f68ad3c0ff48)


## STEP 4-CONFIGURE BUCKET PERMISSIONS

### 1.Before Configuring the bucket policy we will see what happend if we do not configure bucket permissions 

### 2.We have uploaded Our website into bucket so now we will check if this website is hosted on S3 or not. For this we have to paste the endpoint URL in new window after we done this it will shows [ 403 Forbidden ].

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/87ccb330-eb48-4963-84c6-c9771bbdfb57)

### 3.Here we get 403 forbidden because we did not  allow public access to the bucket.So inorder to give public access we have to configure bucket permissions 

### 4.In the bucket properties, go to the “Permissions” tab and Under the “Bucket policy,” click “Edit.”

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/aaf47264-9ace-417e-8849-bc9c92f9c5c8)

### 5.Add the following bucket policy, replacing “your-bucket-name” with your actual bucket name:

{
    "Version": "2012-10-17",
    
    "Statement": [
    
        {
            "Sid": "PublicReadGetObject",
            
            "Effect": "Allow",
            
            "Principal": "*",
            
            "Action": [
            
                "s3:GetObject"
                
            ],
            
            "Resource": [
            
                "arn:aws:s3:::Bucket-Name/*"
                
            ]
            
        }
        
    ]
    
}



![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/45e4739d-25fa-4762-a77e-5d678815fff6)

### 6.Click On “Save” to save the bucket policy

## All the steps have been completed and the website is ready to view

## STEP 5- VIEW THE WEBSITE

### 1.Inorder to viwe the website  Under Buckets, choose the name of your bucket, Choose Properties and At the bottom of the page, under Static website hosting, copy your Bucket website endpoint and paste it in new window

## This is the endpoint URL:
      http://leela-static-website.s3-website.ap-south-1.amazonaws.com

![image](https://github.com/Leela-88/AWS-PROJECT-1/assets/113762845/d4dae6ed-aba7-444a-a61b-ec98822767b8)

## The website can be viewed and static hosting on AWS using S3 has been completed

# SUMMARY

## Creating, managing, and hosting websites and webpages and sharing data publicly is very important and crucial as this provides the public face of most brands and organizations. Looking at this perspective, AWS has developed a great idea to publicly provide an easy and simple solution for their users to host content using the S3 bucket. 






























 







