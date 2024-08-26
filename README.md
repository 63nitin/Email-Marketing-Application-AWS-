# Serverless Email Marketing Project

This project provides a serverless email marketing solution using AWS services like Lambda, S3, SES, EventBridge, and IAM. It automates sending personalized emails to target users based on CSV data stored in S3.

## Project Overview

This project automates the email marketing process using a serverless architecture. By leveraging AWS Lambda for computation, S3 for storage, SES for email sending, and EventBridge for scheduling, this project ensures a scalable and cost-effective email marketing solution.

# What You Need To Follow Along
  1. Email Address that you can validate
  2. An email that can you validate(Need to be form a domain)
  3. Basic knowledge of AWS
  4. A text editor  to write HTML code or Use my code provide in the repo <a>email.html</a>

 ## Architecture Diagram

 ![Architecture Diagram](https://github.com/user-attachments/assets/b5255aa8-3e02-4866-bf17-005e4c84c308)

 ## High Level Requirment
  1. A place to store email templete and list of contact. (CSV file)
  2. A way to send email (SES)
  3. A way to merge email with contact and send them to services. (Lambda)
  4. A way trigger mail to sending on a schedule. (AWS EventBrige)
  5. Clean-up.

## Go through 

### Step 1. AWS S3 Bucket Setup
  1.Open the Amazon S3 console.
  2.Click Create Bucket
  3.Name the bucket (e.g., email-marketing-project) and keep the settings as default.
![](https://github.com/user-attachments/assets/68e79067-c89a-4c93-ae22-42defbe6b40d)

### Step 2. Upload Contacts.csv and eamil.html file in the bucket.
   ![Screenshot 2024-08-26 155110](https://github.com/user-attachments/assets/cad04329-6b29-4eb2-937f-659f9e6f25b3)

### Step 3. AWS SES Verification.
  1. Search "SES"
     ![Screenshot 2024-08-26 155247](https://github.com/user-attachments/assets/c83669e3-6d07-4ad0-9782-229d3a5b0ed6)
  2. Setup By verify your mail.
     ![Screenshot 2024-08-26 160652](https://github.com/user-attachments/assets/2bf8505e-f863-47d7-86b0-19c85dd9bbd0)
  3. Create "Identity" Min 2.
     ![Screenshot 2024-08-26 160806](https://github.com/user-attachments/assets/55f5fd9c-8fb1-4b92-8fbd-33c68bd6e782)
  4. Verify Mail and Domain
      ![Screenshot 2024-08-26 161146](https://github.com/user-attachments/assets/1c7b9c61-a2cd-4ff3-bca0-2eb187058112)

### Step 4. Lambda Function Configuration.
  1. Serch "Lambda".
     ![Screenshot 2024-08-26 161427](https://github.com/user-attachments/assets/cc47c3b9-583f-4669-a225-164362e1f716)
  2. Create Fuction as in the Image. 
     ![Screenshot 2024-08-26 161649](https://github.com/user-attachments/assets/e37076cd-de58-4669-a76b-236b3187df92)
  3. ![Screenshot 2024-08-26 162241](https://github.com/user-attachments/assets/15e49ad5-5e42-4cc1-837e-c3b03d9a0a67)
  4. Copy the Python file in the code section.
     ![Screenshot 2024-08-26 162638](https://github.com/user-attachments/assets/aa4a5ac4-72a1-4fc9-914e-6d2ec6c9daf0)
  5. Test and Deploy using the buttons.
     ![Screenshot 2024-08-26 170302](https://github.com/user-attachments/assets/99b47f7b-2260-441a-b8d2-3b8bc9386e1b)
  6. Handle the AccessDenied Error in testing Phase. Using IAM user functionality Policy and Role as next in STEP 5.

### Step 5. Create Policy.
  1. Search IAM and go to Role and paste AMIpolicyForSES in the json formate
     ![Screenshot 2024-08-26 171617](https://github.com/user-attachments/assets/8b7b5b9f-e7d6-4e12-882a-d9d0d11842f4)
  2. Go to Policy
     ![Screenshot 2024-08-26 171650](https://github.com/user-attachments/assets/e6130f5c-cacd-4762-bc78-350d56268613)
  3. Type code in the json section as in the Image
     ![Screenshot 2024-08-26 172029](https://github.com/user-attachments/assets/b0f97caf-d7bc-4a8a-bbe0-306d9cc07b3a)
  4. ![Screenshot 2024-08-26 172106](https://github.com/user-attachments/assets/a8a30b8b-5da5-4538-8aab-082e3ca131e8)
  5. ![Screenshot 2024-08-26 172122](https://github.com/user-attachments/assets/f781c928-c5f4-46b5-b22a-1bc62e4405c8)
  6. Add the Policy in the Role
     ![Screenshot 2024-08-26 172415](https://github.com/user-attachments/assets/ca3ad85b-31a0-4d54-9b00-c491a084cb25)
  
### Step 6. EventBridge Rule Configuration.
  1. Search EventBridge
     ![Screenshot 2024-08-26 194319](https://github.com/user-attachments/assets/e1e51bb2-8527-4c54-96d9-b45a22778fb0)
  2. ![Screenshot 2024-08-26 194405](https://github.com/user-attachments/assets/846312d8-aa22-4a83-9a96-6c9bccd6c7a0)
  3. ![Screenshot 2024-08-26 194800](https://github.com/user-attachments/assets/a9dcfe8c-8fb1-4af1-b0a3-6080144f6c90)
  4. ![Screenshot 2024-08-26 194839](https://github.com/user-attachments/assets/03b24753-24d5-4314-94af-243496b3bb8f)
  5. ![Screenshot 2024-08-26 195000](https://github.com/user-attachments/assets/136664fc-ae13-4e4c-b6bd-1823282168f3)
  6. ![Screenshot 2024-08-26 195145](https://github.com/user-attachments/assets/29e0d71e-f737-42ac-8ebc-5890e1c493c7)
  7. ![Screenshot 2024-08-26 195216](https://github.com/user-attachments/assets/d00e9ad5-6aad-47d7-9e8b-f8fee734c55d)

### 7. Email Output(check your given mail)
  ![Screenshot 2024-08-26 223020](https://github.com/user-attachments/assets/aab10e9d-476a-4579-9e6e-1f8111c374b4)

### Project Completion Time
  . Approximately 2-3 hours, depending on the complexity Sevices Like use of DynamoDM insteed of CSV file.

  
















    
  






