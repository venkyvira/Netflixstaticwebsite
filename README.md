# Setting Up an S3 Bucket for Static Website Hosting

## Steps to Create and Configure the S3 Bucket

1. **Sign in to AWS Management Console**
   - Go to the AWS Management Console and log in with your credentials.

2. **Select the AWS Region**
   - Ensure you are in the region where you want to create your S3 bucket. For this project, select **US-WEST-2 (Oregon Region)**.

3. **Navigate to S3 Service**
   - In the AWS Management Console, search for and select **S3**.

4. **Create the Bucket**
   - Click on the **Create bucket** button.

5. **Provide Bucket Details**
   - Enter a unique name for your bucket.
   - Choose **US-WEST-2 (Oregon Region)** as the AWS Region.

6. **Enable ACLs**
   - Under "Object Ownership," select **ACLs enabled**.

7. **Configure Public Access Settings**
   - Under **Block all public access**, uncheck this option to allow public access.
   - Acknowledge the risks by checking the acknowledgment box.

8. **Finalize Bucket Creation**
   - Click **Create bucket**.

## Adding a Bucket Policy for Public Access

9. **Access Bucket Permissions**
   - In the S3 dashboard, select your newly created bucket.
   - Navigate to the **Permissions** tab.

10. **Edit the Bucket Policy**
    - Scroll to the **Bucket policy** section and click **Edit**.
    - Add the following policy, replacing `YOUR_BUCKET_NAME` with your bucket's name:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AddPerm",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
    }
  ]
}
```

11. **Save the Policy**
    - Click **Save changes** at the bottom of the page.

    - Ensure there are no errors. Verify the bucket name in the policy if necessary.

## Enabling Static Website Hosting

12. **Navigate to Properties**
    - Go to the **Properties** tab of your bucket.

13. **Enable Static Website Hosting**
    - Scroll to the **Static website hosting** section and click **Edit**.
    - Select **Enable** and choose **Host a static website**.

14. **Configure Website Details**
    - Provide the following details:
      - **Index document**: `index.html`
      - **Error document** (optional): `error.html`
    - Click **Save changes**.

## Upload Website Files

15. **Go to Objects Tab**
    - Navigate to the **Objects** tab and click **Upload**.

16. **Add Files and Folders**
    - Click **Add files** to upload your static website files (e.g., `index.html`, `style.css`, JavaScript, images).
    - Add folders for organizing assets like CSS and images.

## Access Your Static Website

17. **Retrieve the Website Endpoint**
    - Go to the **Properties** tab and scroll to the **Static website hosting** section.
    - Copy the **Bucket website endpoint URL**.

18. **Open in Browser**
    - Paste the URL into your browser's address bar.
    - Your static website should load successfully.

---

_Add images here to illustrate key steps._
