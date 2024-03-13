# Video Streaming with AWS S3 and CloudFront

This project demonstrates how to set up video streaming using Amazon S3 for storage and AWS CloudFront for efficient content delivery. In this example, we use a sample video from the Kannada movie "KGF 2" stored in an S3 bucket, and CloudFront is configured to deliver the content globally with low latency.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Overview](#overview)
- [Setup Instructions](#setup-instructions)
  - [1. Create an S3 Bucket](#1-create-an-s3-bucket)
  - [2. Create a CloudFront Distribution](#2-create-a-cloudfront-distribution)
  - [3. Update S3 Bucket Policy](#3-update-s3-bucket-policy)
  - [4. Access the Video in Browser](#4-access-the-video-in-browser)
- [Contributors](#contributors)
- [License](#license)

## Prerequisites

- [AWS Account](https://aws.amazon.com/)
- [AWS CLI](https://aws.amazon.com/cli/) (optional, for command-line setup)

## Overview

Amazon S3 is used to store the video file, and AWS CloudFront is employed as a content delivery network (CDN) to distribute the video efficiently. The S3 bucket is configured to allow CloudFront to access the stored objects, ensuring secure and fast content delivery.

## Setup Instructions

### 1. Create an S3 Bucket

- Define a unique name for your S3 bucket.
- Use the AWS Management Console or AWS CLI to create the bucket.
- Upload your sample video file (e.g., from the movie "KGF 2") to the S3 bucket.

### 2. Create a CloudFront Distribution

- Navigate to the [AWS CloudFront console](https://console.aws.amazon.com/cloudfront/).
- Create a new distribution with your S3 bucket as the origin.
- Configure the distribution settings, such as the default cache behavior, origin settings, and other options.

### 3. Update S3 Bucket Policy

- Modify the bucket policy to allow CloudFront to access objects. Use a policy similar to the following:

  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Principal": {
          "AWS": "arn:aws:iam::cloudfront:user/CloudFront Origin Access Identity YOUR-CLOUDFRONT-DISTRIBUTION-ID"
        },
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::your-s3-bucket-name/*"
      }
    ]
  }
