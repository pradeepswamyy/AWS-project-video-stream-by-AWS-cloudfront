

# Secure Video Streaming with AWS S3 and CloudFront

This repository contains the necessary configurations to set up a secure video streaming solution using AWS S3 and CloudFront.

## AWS Configuration:

**Create an S3 Bucket:**
1. Log in to the AWS Management Console.
2. Navigate to the S3 service.
3. Click on "Create Bucket."
4. Provide a unique bucket name and choose a region.
5. Configure other settings as needed and create the bucket.

**Upload the Sample Video File:**
1. Open the newly created S3 bucket.
2. Click on "Upload" and select the "KGF2_scene.mp4" file.
3. Configure permissions if required.

## CloudFront Setup:

**Create a CloudFront Distribution:**
1. Navigate to the CloudFront service in the AWS Management Console.
2. Click on "Create Distribution."
3. Choose "Web" distribution.
4. Set the S3 bucket as the origin.
5. Configure other settings according to your requirements.

**Configure Basic Settings and Security Options:**
1. Set the appropriate alternate domain name (CNAME) and other settings.
2. Choose your preferred security policies (HTTP to HTTPS redirect, etc.).

**Modify Bucket Policy for CloudFront Access:**
1. Update the S3 bucket policy to grant access to the CloudFront distribution.
   An example bucket policy is provided in the documentation.
   {
  "Version": "2012-10-17",
  "Id": "PolicyForCloudFront",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::cloudfront:user/CloudFront Origin Access Identity YOUR_CLOUDFRONT_ORIGIN_ACCESS_IDENTITY"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-s3-bucket-name/*"
    }
  ]
}


## Access the Video:

1. Open Your Browser.
2. Enter the CloudFront Distribution URL with Access Credentials, for example, `https://your-cloudfront-domain.com/KGF2_scene.mp4`.
3. Enjoy watching the securely delivered sample video.



---
