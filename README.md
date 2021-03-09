# Deploying Your Capstone with Amazon Web Services Elastic Beanstalk

## Amazon Web Services (AWS)
AWS, a subsidiary of Amazon, is the leading provider of on-demand cloud computing 
platforms and APIs. According to 
[Canalys](https://www.canalys.com/newsroom/global-cloud-market-q4-2020), AWS owns 
around one third of the cloud computing market and has reported revenue of $12.7 billion 
for Q4 2020. Your ability to display your capstone on AWS servers will signal to 
employers you ability to work on a modern software development team, many of which are 
now responsible for the deployment, monitoring, and maintenance of their software 
stack in the cloud.

## AWS Elastic Beanstalk
AWS developed Elastic Beanstalk to facilitate the deployment of web applications with 
AWS managed services. It orchestrates the provisioning and monitoring of the 
infrastructure necessary to manage a scalable and secure web application developed 
with Java, .NET, PHP, Node.js, Python, Ruby, or Go.

## Getting Started

### AWS Account
Working with AWS Elastic Beanstalk requires an AWS account. Fortunately, as of March 
2021 this remains free. Amazon offers an extended free-tier account that gives free 
access for one year to all the services you will need to deploy your application with 
Elastic Beanstalk. Even still, note that setting up an AWS account requires an active 
credit card, which will be billed if your usage exceeds the free tier limit. These 
instructions will teach you how to set up daily billing alerts as an additional tool 
to prevent unwanted charges.

#### Creating and Activating Your Account
1. Open the [Amazon Web Services home page](https://aws.amazon.com/).
2. Choose **Create an AWS Account**.
3. Enter your account information. Document the information securely and then choose 
   **Continue**.
4. Choose **Personal**.
5. Enter your personal information.
6. Enter your billing information.
7. Confirm your identity with a phone number.
8. Enter the verification code.
9. Select the **Basic Plan**.

You will receive an email to confirm that your account has been created. Once that 
happens, you can access your account with the email address and password you used to 
register. 

#### Setting Up an IAM User and Root Multi-factor Authentication
1. Open the [Amazon Web Services home page](https://aws.amazon.com/).
2. Choose **Sign In to the Console**.
3. Sign in as the **Root user**.
4. [Set up a virtual Multi-factor Authentication device for your AWS account root user.
   ](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_virtual.html#enable-virt-mfa-for-root)
5. Navigate to **IAM** with the search bar at the top of the screen.
6. Choose **Users** on the left navigation menu.
7. Select **Add user**.
8. Enter a **User name** and check both **Programmatic** and **AWS Management 
   Console** access.
9. Choose a **Console password** type and determine whether you would like to 
   **Require password reset** for the user at initial sign-in.
10. Choose **Next: Permissions**.
11. Choose **Create group**.
12. Enter `Admin` in the **Group name** box and select **Administrator Access** in the 
    policy name menu.
13. Choose **Create group**.
14. Choose **Next: Tags**.
15. Choose **Next: Review**.
16. If all looks as you expect, choose **Create User**.

#### Setting Up a Budget
1. Choose **My Account** from the account dropdown menu in the top right corner of the 
   screen.
2. Scroll down to **IAM User and Role Access to Billing Information** and select **edit**.
3. Select **Activate IAM Access** and **Update**.
4. Document all credentials securely: root user email address; root user password; IAM 
   username; IAM password, and account number. 
   
**Store this information in the securest manner possible. Consider using a password manager 
such as LastPass or One Password. Your finances are now tied to these credentials. In the 
wrong hands, an AWS account can accrue charges rapidly, even with a daily budget.**

5. **Sign out** of the Root account through the account dropdown menu in the top right 
   corner of the screen.
   
A Note on the Root User
It is widely considered bad practice to perform tasks with the root user. The root user 
should only be used to create the first IAM user, to open billing privileges to administrators, 
and to close the account. Store the credentials securely.

6. Open the [Amazon Web Services home page](https://aws.amazon.com/).
7. Choose **Sign In to the Console**.
8. Sign in as the **IAM user** you created above.
9. Use the search console to find **AWS Budgets**.
10. Choose **Create budget**.
11. Select **Cost budget**.
12. Name the budget. Choose **Daily** for the **Period**. Select **Recurring budget** and 
    **Fixed**. Enter $0.01 as the **Budgeted Amount**.
13. Choose **Configure thresholds**.
14. Set threshold based on **Actual cost**.
15. Set up notifications by entering an email address in the **Email recipients** box. 
16. Choose **Confirm budget**.

#### IAM Multi-factor Authentication
1. [Set up multi-factor authentication for your IAM user.](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_virtual.html)
2. **Sign out** of your AWS account through the account dropdown menu in the top 
    right corner of the screen.

### Installing the Elastic Beanstalk CLI



