+++
title = "Amazon Q Developer operational investigations"
date = 2024-05-14T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>3.2 </b>"
+++

### What is Amazon Q Developer Operational Investigations?

Amazon Q’s operational investigations feature helps you quickly investigate and resolve incidents by surfacing relevant information, leveraging the power of generative AI technology. Amazon Q will scan metrics, logs, traces, deployment events, and other data to generate root cause hypotheses and actionable insights.

### Getting Started

1. Open the [CloudWatch console](https://console.aws.amazon.com/cloudwatch/)
2. In the left navigation pane

- choose **AI Operations**
- choose **Investigations**
- Choose Configure for this account. (Please note: To create an investigation group and set up Amazon Q Developer operational investigations, you must be signed in to an IAM principal that has the either the **AIOpsConsoleAdminPolicy** or the **AdministratorAccess** IAM policy attached, or to an account that has similar permissions. Settings in the investigation group help you centrally manage the common properties of your investigations)

![Investigations-1](/images/4/investigations-1.png?width=90pc)

4. Select the retention period for investigations. The default is 90 days.
5. You can optionally customize the encryption settings. For example: if you would like to use a customer managed key instead of the default one provided by AWS. For more information, see [Encryption of investigation data](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-Security.html#Investigations-KMS).

![Investigations-2](/images/4/investigations-2.png?width=90pc)

6. (Optional) The user access section of the getting started wizard helps you understand how to set up appropriate permissions for different user roles interacting with Amazon Q Developer operational investigations. (The link will take you the documentation with more information) AWS provides three managed IAM policies: **AIOpsConsoleAdminPolicy** for administrators, **AIOpsOperatorAccess** for users who need to start and manage investigations, and **AIOpsReadOnlyAccess** for users who only need to view information.

![Investigations-3](/images/4/investigations-3.png?width=90pc)

7. You can optionally connect Amazon Q Developer operational investigations to IAM Identity Center. By integrating with IAM Identity Center, you can attribute the suggestions added to the investigation feed, back to individual users. For more information, please see this [link](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-Integrations.html#Investigations-Integrations-IDC).

![Investigations-4](/images/4/investigations-4.png?width=90pc)

8. Choose **Next** to continue
9. In the “Investigation configuration” section, you can setup the IAM role that Q Developer will use to access telemetry data for its investigations. Select “Auto-create”. This will create a configure the new role with the required permissions.

![Investigations-5](/images/4/investigations-5.png?width=90pc)

10. Under the **Enhanced integration** section, you can configure additional options that will further assist Q developer in performing the investigation. The next steps will briefly explain what these options do.
11. **Tags for application boundary detection**: This section allows you to specify existing custom tag keys used for your applications. These tags help Amazon Q Developer refine its search when discovering resource relationships. More information can be found [here](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-GetStarted.html).

![Investigations-6](/images/4/investigations-6.png?width=90pc)

12. The **CloudTrail section for change event detection** lets Amazon Q Developer access CloudTrail data, improving its analysis of system changes and root cause hypotheses.

![Investigations-7](/images/4/investigations-7.png?width=90pc)

13. The **X-Ray for topology mapping** and **Application Signals for health assessment** sections highlight additional AWS services that can enhance Amazon Q Developer’s capabilities.

![Investigations-8](/images/4/investigations-9.png?width=90pc)

14. Choose “**Next**” to continue
15. The last section of the wizard allows to configure third party integrations. Those include ticketing systems, chat integration, and SNS. We won’t cover those in-depth here. But if you like more information, please visit this [link](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-GetStarted.html).
16. Choose “**Complete setup**” to start the configuration. After a few seconds, you will see a message confirming “**Initial Setup success**”

![Investigations-9](/images/4/investigations-10.png?width=90pc)
