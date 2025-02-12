# Implementing-Text-to-Speech-TTS-with-Amazon-S3-AWS-Lambda-and-Amazon-Polly
Converting text files stored in an S3 bucket into speech using Amazon Polly and save the generated audio back to S3. 

Step 1: Create 2 buckets in S3

![Screenshot 2025-02-11 203106](https://github.com/user-attachments/assets/b0b1fb69-9518-4d3f-86d2-4d4097fad9d6)

Name the 1st bucket as aws-polly-source-bucket

![Screenshot 2025-02-11 203200](https://github.com/user-attachments/assets/7319d006-aa39-469a-9aab-e89df9eaecbc)

Name the 2nd bucket as aws-polly-des-bucket

![Screenshot 2025-02-11 203300](https://github.com/user-attachments/assets/f4392545-89d1-4b4a-9f26-2ae4fc4b088c)

Both have been created successfully

![Screenshot 2025-02-11 203321](https://github.com/user-attachments/assets/d4e9c29e-901e-42da-98a0-ec79ab7dc28b)

Step 2: Go to IAM and click Create Policy

![Screenshot 2025-02-11 203406](https://github.com/user-attachments/assets/445ad49a-a2d5-47fd-ba66-f1ff4c003f52)

Click Specify permissions and In policy editor press JSON and write this policy

![Screenshot 2025-02-12 054834](https://github.com/user-attachments/assets/025669f9-eefc-4eb1-8e74-f8a9494d0d5e)

IAM Policy Name: aws-polly-lambda-policy

![Screenshot 2025-02-11 203634](https://github.com/user-attachments/assets/bfb0b02d-90e8-48fd-b794-002040d432a6)

Policy has been created

![Screenshot 2025-02-11 203709](https://github.com/user-attachments/assets/62602c26-f822-4883-b3a5-5ea8638b60c8)

Step 3: Create an IAM Role (IAM Role Name: aws-polly-lambda-role) and attach aws-polly-lambda-policy and AWSLambdaBasicExecutionRole Policies

![Screenshot 2025-02-11 204758](https://github.com/user-attachments/assets/1ce4c1c8-7e15-4a72-b655-c730c218ffbe)

![Screenshot 2025-02-11 204830](https://github.com/user-attachments/assets/60aec8b2-0a82-4b17-8d0f-2fcab2461230)

![Screenshot 2025-02-11 204919](https://github.com/user-attachments/assets/c4433e95-5219-4365-891b-88ca1ca76d5e)

![Screenshot 2025-02-11 204919](https://github.com/user-attachments/assets/988f2e75-9300-4bb8-8183-76dad51f9d41)

![Screenshot 2025-02-11 204957](https://github.com/user-attachments/assets/389cca75-9f10-4cc1-bffb-81af4eeba314)

![Screenshot 2025-02-11 205024](https://github.com/user-attachments/assets/e63ed700-575d-417a-b3e1-317a1907c241)

![Screenshot 2025-02-11 205114](https://github.com/user-attachments/assets/51519c09-e9b6-4dd5-9c1a-addf14693b16)

Both the policies were created successfully

Step 4: Create and Configure the Lambda Function (Lambda Function Name: TextToSpeechFunction)

![Screenshot 2025-02-11 205229](https://github.com/user-attachments/assets/be91e3c5-4b63-4b96-aa99-afdbc977f9ae)

![Screenshot 2025-02-11 205313](https://github.com/user-attachments/assets/6dc4c1c7-ef53-49b4-bbe7-85d48b86bd5e)

![Screenshot 2025-02-11 205334](https://github.com/user-attachments/assets/1be876e6-5142-4a5c-bd59-a53e06e5087e)

![Screenshot 2025-02-11 205503](https://github.com/user-attachments/assets/892b3897-aa02-4ceb-8e9e-0417b14b9a43)

![Screenshot 2025-02-11 205630](https://github.com/user-attachments/assets/3992a1e0-40f3-4c39-99d5-0192b61576d0)

![Screenshot 2025-02-11 205738](https://github.com/user-attachments/assets/271df651-880a-45ae-962c-71f4676fafa6)

Step 5: Configure S3 Event Notification

![Screenshot 2025-02-11 205852](https://github.com/user-attachments/assets/03c7d3af-573e-49bd-92cd-520e807df00f)

Set up an event notification in the source S3 bucket to trigger the Lambda function on new object creation events with the .txt suffix.

![Screenshot 2025-02-11 205910](https://github.com/user-attachments/assets/4e8fe9e4-fec0-4406-bc3f-15ff6ae4c887)

Trigger successfully added

![Screenshot 2025-02-11 210038](https://github.com/user-attachments/assets/cc5c0d71-93af-4411-945e-820464852a85)

Upload an file aws.txt in aws-polly-source-bucket

![Screenshot 2025-02-11 210212](https://github.com/user-attachments/assets/a52c4f05-1d12-4203-8d92-958ba9ece9d2)

![Screenshot 2025-02-11 210338](https://github.com/user-attachments/assets/ae770cdd-2be6-4c24-9d6d-f777140dc1eb)


Step 6: Write Lambda Function Code

I have attached that file as TextToSpeechFunction.py

![Screenshot 2025-02-11 210404](https://github.com/user-attachments/assets/4bf3a571-7e62-48f6-a13f-552b3d62be26)

Step 7: Test the System

![Screenshot 2025-02-11 210606](https://github.com/user-attachments/assets/27fb8856-181e-43c2-9c9f-a2c3202497d5)

![Screenshot 2025-02-11 212923](https://github.com/user-attachments/assets/8a59bbe5-44d3-459d-987b-56c7e8895ad4)










