# Project Name:  Video Hosting with AWS S3 and CloudFront

## Overview:
This project demonstrates the setup and configuration of Amazon S3 (Simple Storage Service) and CloudFront to host and deliver a sample video clip from the popular Kannada movie "KGF 2". By leveraging these AWS services together, we ensure efficient and secure delivery of video content while enhancing performance and user experience.

## Requirements:
- An AWS account
- Basic familiarity with AWS services (S3, CloudFront)
- Sample video file (e.g., a clip from "KGF 2")

## Steps:
1. **Create an S3 Bucket:**
   - Create a new S3 bucket to store the sample video file.

2. **Access Initial Issues:**
   - Attempt to access the sample video directly through its S3 object URL. Encounter restrictions due to the initial bucket policy.

3. **Set up CloudFront Distribution:**
   - Create a CloudFront distribution specifically for the video sample.
   - Configure essential options such as origin settings, caching behavior, and distribution settings.

4. **Update Bucket Policy:**
   - Update the bucket policy to allow seamless media streaming via CloudFront. Ensure proper permissions are set.

5. **Test Setup:**
   - Copy and paste the CloudFront distribution domain name and any required query parameters or object keys into a web browser.
   - Verify that the video plays without encountering previous permission-related obstacles.

6. **Finalize Configuration:**
   - Adjust CloudFront settings as necessary for optimal performance and security.
   - Ensure proper monitoring and logging are enabled for the CloudFront distribution.





