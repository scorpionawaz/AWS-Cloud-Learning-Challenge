# Hosting a Static Website on Amazon (AWS) S3

Amazon Web Services (AWS) offers a simple and cost-effective solution for hosting static websites using Amazon S3 (Simple Storage Service). This is a very good beginner project for those who are exploring AWS. In this guide, I will walk you through the process of hosting a static website on Amazon S3.

## PREREQUISITE

- An AWS account (sign up at [AWS](https://aws.amazon.com/) if you don’t have one)
## STEP 1: CREATE A S3 BUCKET

1. Log in to your AWS Management Console.

   
   ![AWS Management Console](screenshots/Management%20Console.png)

   
2. Choose the region closest to your target audience or your residence region.


![choose region](screenshots/Setting%20Region.png)


3. Navigate to the Amazon S3 service.


  ![Search S3](screenshots/Searching%20Service.png)


4. Click "Create bucket" to begin creating a new bucket.

   ![Create Bucket](screenshots/Create%20Bucket%20Button.png)


5. Provide a unique name for your bucket 


    ![Enter Name](screenshots/Enter%20%20Name.png)


6. Uncheck ‘Block all public access’ to make all the objects in the bucket public.


   ![Public Access](screenshots/Unblock%20Public%20Access.png)


7. Keep the default settings for the rest of the options and click "Create" to create the bucket.


    ![Click Create](screenshots/Create%20Bucket.png)


## STEP 2: ENABLE STATIC WEBSITE HOSTING


1. Once your bucket is created, select it from the list and go to the “Properties” tab.


2. Scroll down to the “Static website hosting” section and click “Edit.”


   ![Static Website Hosting](screenshots/Enable%20Static%20Web%20Hosting.png)


3. Select "Enable" for the "Static website hosting" option.


4. Enter the name of your default HTML file which you are going to use for hosting (e.g., `index.html`).


5. Click "Save" to save the changes.


## STEP 3: UPLOAD THE WEBSITE CONTENT


1. After creation and opening of same bucket you will be directed into object tab.


2. Click "Upload" to upload your website files to the bucket.


   ![Upload Files](screenshots/Add%20files.png)


3. Select the website files of your project

![Upload Files](screenshots/select%20files%202.png)

4. Click "Upload".




## STEP 4: CONFIGURE BUCKET PERMISSIONS

1. In the bucket properties, go to the “Permissions” tab.
    ![Permission Tab](screenshots/Go%20to%20permissions.png)

2. Under “Bucket policy,” click “Edit.”

3. Add the following bucket policy, replacing `your-bucket-name` with your actual bucket name:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::your-bucket-name/*"
       }
     ]
   }
   ```

   ![Bucket Policy](screenshots/Add%20bucket%20policy.png)

4. Click "Save" to save the bucket policy.

## STEP 5: VIEW THE WEBSITE

1. Click on the `index.html` file from the Objects tab and Click ‘Open’.

   ![View Website](screenshots/Ready%20to%20view.png)

The website can be viewed, and static hosting on AWS using S3 has been completed.


