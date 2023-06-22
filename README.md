# OCR using Amazon Textract

Optical Character Recognition WebApp that allows user to upload their document for scanning and returns the extracted text from document to users on webpage.

## Tech Stack

• AWS Textract

• AWS Simple Storage Service (S3) - Buckets

• Python 

• Flask
## Documentation

1. Create AWS Account, and apply for free tier 12 months subscription using Card details (0 fees to be paid).

2. `Create a bucket` 
   
    • Name the bucket

    • Object Ownership - ACL's enabled
    
    • Block all public access settings (Uncheck All)

    • Disable Bucket Versioning

    • Default Encryption - keep as it is

    • Click on Create Bucket

3.  After creation of bucket under Access control list (ACL)

    • Edit and Grant following permission

        1) `Bucket Owner` - Objects (List, Write), Bucket ACL (Read, Write)
    
        2) `S3 Log delivery group` - Bucket ACL (Write)
    
    • Save settings

4. Create Identity and Access Management (IAM) User and grant full programmatic access to AWS Textract and S3 Bucket.

    • Enter name of user

    • Click Next

    • In Permissions options, check on Attach policies directly

    • Under Permissions policies, search "AmazonS3FullAccess" and "AmazonTextractFullAccess" and check right beside that policies to give to the user.

    • `Create User`

    • Now go to Security Credentials after creating user, and create new Access SSH key by scrolling below.

    • Download CSV files containing both Access Key and Secret Access Key as it is only one time downloadable and after that it will not show again on user details.

5. Now copy paste both keys in app.py file of my project

6. Change bucket name to yours

7. Here i have imported cred file from my project as it contains both keys so making it confidential, but you have to use your own keys. And remember during uploading your code to github dont show your keys instead use .gitignore method to hide from public.

8. On line 70 of app.py there is a key="", it is useful for finding and extracting the specific words from scanned or uploaded document, if key="Pay" - then value or text pertaining to "Pay" in the document will be extracted. If key="" kept empty then all text is extracted as per it's accuracy.

## Snapshots

### Webapp Layout

![webapp-layout](https://github.com/meet2632/OCR-webapp-using-Textract/assets/80049664/c4f80d47-672d-47b9-b8ee-f762f0bdf5b3)
### Extraction Proof

![extraction-successful](https://github.com/meet2632/OCR-webapp-using-Textract/assets/80049664/08262699-b2a2-4309-9aae-3a4efdfde4b6)
