+++
title = "Amazon Q Developer in Visual Studio Code"
date = 2024-05-14T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>3.1 </b>"
+++

#### Install the Amazon Q extension in Visual Studio Code

Visual Studio Code is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux. Ensure you have installed [Visual Studio Code](https://code.visualstudio.com/download) for your operating system. You can find the [setup](https://code.visualstudio.com/docs/setup/setup-overview) steps in their official documentation.

#### Install the Amazon Q extension

1. Open **Visual Studio Code**
2. Click on **Extensions** on the left activity bar.
3. In the extensions, search for "**Amazon Q**".
4. Select **Install** the extension, restart/reload VSCode if required.

![AmazonQ-1](/images/3/AmazonQ-1.png?width=90pc)

#### Authenticate

You have 2 options to sign-in and this workshop explores both the authentication methods:

1. with [Builder ID](https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/builder-id.html) for Individual users with Free Tier
2. with [AWS IAM Identity Center](https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/sso-credentials.html) for Professional users with Pro Tier

You might use a workforce identity in IAM Identity Center to represent your work-self and an AWS Builder ID to represent your private-self. These identities operate independently. [Amazon Q Developer Pricing](https://aws.amazon.com/q/developer/pricing/) for more details.

![AmazonQ-2](/images/3/AmazonQ-2.png?width=90pc)
_Source: **Amazon Q Developer Pricing**_

In the Visual Studio Code, Open Amazon Q from the left Activity Bar. You will be presented with following screen:

![AmazonQ-3](/images/3/AmazonQ-3.png?width=90pc)

#### With AWS Builder ID (no AWS account required)

Choose this option to use Amazon Q for free. You do not need an AWS Account, however, you do need to sign up for an AWS Builder ID. [AWS Builder ID](https://docs.aws.amazon.com/signin/latest/userguide/sign-in-aws_builder_id.html) is a personal profile that provides access to [select tools and services](https://docs.aws.amazon.com/signin/latest/userguide/aws_builder_id-apps.html). AWS Builder ID is free. You only pay for the AWS resources you consume in your AWS accounts, which is separate from Builder ID. You can use the same email for your AWS Builder ID and for the root user email of an AWS account.

1. Select on the first option "**Use for Free**" and click "**Continue**".
   ![AmazonQ-4](/images/3/AmazonQ-4.png?width=90pc)

2. Enter your email address, click **Next**
   ![AmazonQ-5](/images/3/AmazonQ-8.png?width=90pc)

3. Enter your name, click **Next**
   ![AmazonQ-6](/images/3/AmazonQ-9.png?width=90pc)

4. Enter verification code sent to your email, click **Verify**
   ![AmazonQ-8](/images/3/AmazonQ-10.png?width=90pc)

5. Enter your **password** and type the **CAPTCHA**
   ![AmazonQ-9](/images/3/AmazonQ-11.png?width=90pc)

6. Enter the **email address** you used to register for your Builder ID, click **Next**
   ![AmazonQ-7](/images/3/AmazonQ-18.png?width=90pc)

7. Enter the **password** you used to register for your Builder ID, click **Sign in**
   ![AmazonQ-10](/images/3/AmazonQ-12.png?width=90pc)

8. Enter verification code sent to your email, click **Verify**
   ![AmazonQ-11](/images/3/AmazonQ-13.png?width=90pc)

9. You have successfully created a Builder ID account
   ![AmazonQ-12](/images/3/AmazonQ-14.png?width=90pc)

10. In the Visual Studio Code panel, select **Cancel**
    ![AmazonQ-13](/images/3/AmazonQ-15.png?width=90pc)

11. Select the option "**Use for Free**" and click "**Continue**".
    ![AmazonQ-14](/images/3/AmazonQ-16.png?width=90pc)

12. Click **Open**
    ![AmazonQ-15](/images/3/AmazonQ-17.png?width=90pc)

13. Click **Allow access**
    ![AmazonQ-16](/images/3/AmazonQ-5.png?width=90pc)

14. You have successfully approved the request for AWS IDE Extensions for VS Code
    ![AmazonQ-17](/images/3/AmazonQ-6.png?width=90pc)

15. Once done, you can switch back to your IDE. You have successfully logged into Amazon Q with Builder ID. A Q Chat window should automatically open for you.
    ![AmazonQ-18](/images/3/AmazonQ-7.png?width=90pc)

You can now skip to [**_Ask Amazon Q a question in the IDE_**](Ask Amazon Q a question in the IDE).

#### Pro license with AWS IAM Identity Center

{{% notice warning %}}
**Important!**: _If you are following this step, you will incur AWS charges. If you are just testing this out, make sure to remove the users at the end to reduce the cost._
{{% /notice %}}

To authenticate via this method, it is important to have an AWS Account with activated IAM Identity Centre. Amazon Q requires IAM Identity Center. If your AWS Organization does not have IAM Identity Center activated. The Account Administrator must first activate IAM Identity Center in this account in order to set up Amazon Q.

Request your account administrator to create an identity for you in the IAM Identity Center and [subscribe this identity to Developer Pro](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-pro-tier-setting-up-access.html).

Ensure the Account Administrator shares two key items for you to login via Visual Studio Code:

- Start URL
- AWS Region

These are available in the AWS Console for IAM Identity Center, in the "Settings" section you will the AWS access portal URL under Identity Source tab.

In Visual Studio Code, perform following steps to authenticate:

- Click on "**Amazon Q**" in the Status Bar below for more options like Pause auto-suggestions, open settings or Sign out.
  ![AmazonQ-19](/images/3/AmazonQ-19.png?width=90pc)

1. Access the [Amazon Q](https://us-east-1.console.aws.amazon.com/amazonq?region=us-east-1#)

- Select **Amazon Q Developer**
  ![AmazonQ-1](/images/3/AmazonQpro-1.png?width=90pc)

2. Select **Get started**
   ![AmazonQ-1](/images/3/AmazonQpro-2.png?width=90pc)

- Enter **Email address**, **First name** & **Last name**
- Select **Continue**
  ![AmazonQ-1](/images/3/AmazonQpro-3.png?width=90pc)
- Type **Profile name**
- Select **Create**
  ![AmazonQ-1](/images/3/AmazonQpro-4.png?width=90pc)

3. You have successfully created a profile for Amazon Q Developer.

- Copy Start URL
  ![AmazonQ-1](/images/3/AmazonQpro-5.png?width=90pc)

4. Access your email address

- Select **Accept invitation**
  ![AmazonQ-1](/images/3/AmazonQpro-6.png?width=90pc)

5. At the New User Registration section

- Type the **New password**
- Type the **Confirm password**
- Click **Set new password**
  ![AmazonQ-1](/images/3/AmazonQpro-7.png?width=90pc)

6. Enter **User name** (your email)

- Click **Next**
  ![AmazonQ-1](/images/3/AmazonQpro-8.png?width=90pc)

7. Enter your **Password**

- Click **Log in**
  ![AmazonQ-1](/images/3/AmazonQpro-9.png?width=90pc)

8. At the MFA Device Enrollment section

- Select **Authenticator Application**
- Click **Next**
  ![AmazonQ-1](/images/3/AmazonQpro-10.png?width=90pc)

9. At the **Set up authenticator app**
   {{% notice info %}}
   If you haven’t installed a virtual MFA app, please install it using the link:
   [Authenticator Extension](https://chromewebstore.google.com/detail/authenticator/bhghoamapcdpbohphigoooaddinpkbai)
   {{% /notice %}}

- Click **Show QR code**
  ![AmazonQ-1](/images/3/AmazonQpro-11.png?width=90pc)
- Use the virtual MFA app or your device's camera to scan the QR code.
- Enter **Code from authenticator**
- Click **MFA Designation**
  ![AmazonQ-1](/images/3/AmazonQpro-12.png?width=90pc)

10. Click **Complete**
    ![AmazonQ-1](/images/3/AmazonQpro-13.png?width=90pc)

11. Check the email **Active Your Amazon Q Developer Pro Subscription**
    ![AmazonQ-1](/images/3/AmazonQpro-14.png?width=90pc)

12. On the Sign-in window in Amazon Q, select on the first option "**Use with Pro license**" and click "**Continue**"
    ![AmazonQ-1](/images/3/AmazonQpro-15.png?width=90pc)
13. You will be asked to enter **Start URL** and **AWS Region** we noted earlier.

- Click **Continue**
  ![AmazonQ-1](/images/3/AmazonQpro-16.png?width=90pc)

- You will get a pop-up with a confirmation code, click on "Proceed to browser".

14. You will be redirected to a web browser. Confirm the code is same and click on "**Confirm and continue**".

- This redirects you to sign in to your Identity Center profile. Once done, simply "**Allow access**".
  ![AmazonQ-1](/images/3/AmazonQpro-17.png?width=90pc)

15. You have successfully approved the request for AWS IDE Extensions for VS Code
    ![AmazonQ-1](/images/3/AmazonQpro-18.png?width=90pc)
16. You can now switch back to your Visual Studio Code IDE. You have successfully logged into Amazon Q with Pro license.

- A Amazon Q Chat window should automatically open for you.
  ![AmazonQ-1](/images/3/AmazonQpro-19.png?width=90pc)

#### Ask Amazon Q a question in the IDE

Amazon Q can be found in the activity bar in Visual Studio Code.
![AmazonQAsk-1](/images/3/AmazonQask-01.png?width=90pc)

- Open your source code or a GitHub repository.
- Select code, right click send to Amazon Q to explain code OR open the file and ask Q to explain the code.
  ![AmazonQAsk-2](/images/3/AmazonQask-02.png?width=90pc)
