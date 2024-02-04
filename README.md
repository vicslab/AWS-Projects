# AWS Beginner Projects: Project 1

---

# Hosting a Static Website on AWS S3 with a Custom Domain

This project is designed for beginners looking to set up a personal website using Amazon Web Services (AWS) S3 and connecting it with a custom domain through Amazon Route 53.

## Step 1: Design Your Website

- **Option 1**: Design your own personal website. Utilize HTML and CSS to create a unique site that represents you or your project.
- **Option 2**: Download an existing template. Free templates are available at resources like [free-css.com](https://www.free-css.com/), offering a variety of styles to start with.

## Step 2: Set Up Amazon S3 Bucket

1. **Access AWS Management Console**: Log into your AWS account and open the Amazon S3 console.
2. **Create a New Bucket**:
    - Click "Create bucket".
    - Provide a unique name for your bucket, ideally matching your intended domain name for consistency (e.g., `yourdomain.com`).
    - Select the AWS region closest to your target audience.
    - Uncheck "Block all public access" settings and acknowledge the warning to allow public access.
3. **Enable Static Website Hosting**:
    - In the "Properties" tab, find the “Static website hosting” option and click “Edit”.
    - Select “Enable” and enter the name of your main HTML file (e.g., `index.html` or `vicslabsproject.html`) as the index document.
4. **Upload Your Website Files**:
    - Navigate back to the bucket overview and click "Upload".
    - Select and upload your website files (HTML, CSS, JavaScript, images, etc.).

## Step 3: Set Bucket Permissions

- **Edit Bucket Policy**: In the “Permissions” tab, use the Bucket Policy editor to add a policy allowing public reads. Replace `yourbucketname` with your bucket's actual name:

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Sid": "PublicReadGetObject",
    "Effect": "Allow",
    "Principal": "*",
    "Action": "s3:GetObject",
    "Resource": "arn:aws:s3:::yourbucketname/*"
  }]
}
```

## Step 4: Purchase and Configure a Custom Domain through Amazon Route 53

1. **Navigate to Route 53**: Access the Route 53 dashboard within the AWS Management Console.
2. **Register a Domain**:
    - Choose “Domain registration” > “Register domain”.
    - Follow the prompts to search for and purchase your custom domain (e.g., `yourdomain.com`).
3. **Connect Your Domain to S3**:
    - In Route 53, go to “Hosted zones” and select your domain.
    - Create a record set to point to your S3 bucket. Select an A record using the Alias option and choose your S3 bucket as the alias target.

## Completion Time

- **Basic Setup**: Approximately 30 minutes to 1 hour if using an existing template.
- **Custom Design**: Additional time may be required for designing or customizing your website.

## Conclusion

Congratulations! You've successfully deployed your personal website on AWS using S3 for hosting and Route 53 for your custom domain. This setup provides a robust and scalable solution for hosting static websites, with the flexibility to update and modify your site as needed.

