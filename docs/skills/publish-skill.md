---
title: Cortana Skills Publishing Process
description: Describes the publishing process for Cortana Skills and how to deploy skills to self, group, and world. 

ms. assetid: 6dad0848-3886-4729-90fa-0bcd424b3561
ms. date: 01/22/2019
ms. topic: article

keywords: cortana
---

# Publishing Cortana Skills  

>[!NOTE]
> This article describes the three deployment groups in Cortana and how to publish a Cortana Skill. You should create a Cortana Skill before proceeding. 
> *   If you have never created a Cortana Skill and need to get started, visit the [Create your first skill](./get-started.md) page.  

Deploy your Cortana Skill to each of the three deployment groups.  
*   [Default Settings](#default-settings)  
*   [Test Group Settings](#test-group-settings)  
*   [World Settings](#world-settings)  

All deployment groups contain the same instance of your Cortana Skill.  
Two identifiers are assigned to your Cortana Skill.  
* `skillId`:  The identifier (ID) of your Cortana Skill is unique per deployment group. If your skill checks the ID, then verify the IDs are different for each group. Use the ID of your Cortana Skill if you want to turn on additional logging for the group environment.  
* `skillProductId`: The product ID of your Cortana Skill is unique across deployment groups.  

Cortana passes these IDs in the channel information of the message.

## Cortana Configuration Fields  

<!-- The following INCLUDE statements was causing trouble with builds, so I just copied the code from the
include file into this file. (DT)
[!INCLUDE [open-configure-cortana](../../includes/open-configure-cortana.md)]
 -->
Follow these instructions to access the Cortana Configuration page and update each of the parameters for your Cortana Skill.

1. Sign into the [BotFramework](https://dev.botframework.com) portal and click on the `My bots` link.  

1. On the *My bots* page, click the name of your bot.  

    ![your Web App Bot blade menu](../media/images/web_app_bot_blade-menu.png)  

1. On the *Microsoft Azure* portal, in your Web App Bot blade, under the *Bot Management* section, click on the **Channels** icon.  

    ![Bot management - Channels](../media/images/bot_management-channels.png)  

1. On the *Connect to channels* page, under the *Add a featured channel* section, click on the **Configure Cortana Channel** icon.  

    ![Configure Cortana](../media/images/configure_cortana.png)

## Default Settings  

After configuring the Cortana channel for your skill, it's automatically deployed to **Default Settings**. Deploying to **Default Settings** makes the skill available to you only, so you can thoroughly test it before deploying it to one of the other environments.  

For more information about configuring the Cortana channel, visit the [Connect a bot to Cortana](https://docs.microsoft.com/azure/bot-service/bot-service-channel-connect-cortana?view=azure-bot-service-3.0) page.

![Default settings](../media/images/default_settings.png)

1. On the *Configure Cortana* page, under the *Default Settings* section, enter the following information.

    Complete the required fields (marked with an asterisk).

    For more information about the bot configuration fields, visit the [Connect a bot to Cortana](https://docs.microsoft.com/azure/bot-service/bot-service-channel-connect-cortana) page.  

    1. Skill information section

    ![Skill information](../media/images/default_settings-skill_information.png)

    * `Skill icon`: Click on the **Upload icon** button and select an icon for your Cortana Skill.  
    * `Display name`: The value is limited to 30 characters.  
    * `Invocation name`: The name used to invoke your Cortana Skill. This value must be unique across Cortana (all Cortana Skills).

        For more information about invocation naming, visit the [Invocation Name Guidelines](./cortana-invocation-guidelines.md) page.  

    1. Manage user identity through Connected Services  
    ![Manage user identity through Connected Services](../media/images/default_settings-manage_user_identity_connected_services-off.png)

        `Cortana should manage my user's identity`: If you select this option, then you must complete the following fields.  

    ![Manage user identity through Connected Services](../media/images/default_settings-manage_user_identity_connected_services-on.png)  

    * `When should Cortana prompt for a user to sign in?`  
        * `Sign in at invocation`: The user signs in once, and the authorization token will be passed as needed.
        * `Sign in when required`: The user will be asked to sign in whenever necessary.

    * `Account name`: The name of your Account.
  
    * `Client ID for third-party services`: The application ID of your bot.  

        If you use a Microsoft service, the you get your application ID on the [Microsoft Application Registration Portal](https://apps.dev.microsoft.com/#/appList) page. Click the name of your BotFramework bot listed under the My Applications section.

    * `Space-separated list of scopes`: The list of scopes, separated by spaces.  
    * `Authorization URL`: The authorization URL of your OAuth 2.0 provider.  

        If you use a Microsoft service, then the authorization URL is:  

        ```url
        https://login.microsoftonline.com/common/oauth2/v2.0/authorize
        ```  

    * `Token options`  
        * Possible values are `GET` or `POST`.  
    * `Grant type`  
        * Possible values are `Authorization code` or `Implicit`.  
    * `Token URL`: The token URL of your OAuth 2.0 provider.

        If you are using a Microsoft service, then set to the following value.  

        ```url
        https://login.microsoftonline.com/common/oauth2/v2.0/token
        ```  

    * `Client secret/password for third party services`  
        * The password of your bot.  

            >[!TIP]
            > If you are using a Microsoft Identity Service, then the password is generated when you registered your bot in the *Microsoft Application Registration* portal.  
            >
            > >[!NOTE]
            > > The Client Secret is displayed only once under the *Application Secrets* section of the [Microsoft Application Registration](https://apps.dev.microsoft.com/#/appList) portal. 
            > > To recreate or reveal the secret password of your application, click on the **Generate New password** button.  

    * `Client authorization scheme`  
        * The client authorization scheme.  
            Possible values are `HTTP Basic (Recommended)` or `Credentials in request body`  

            >[!TIP]
            > If you do not know your client authorization scheme, then set `HTTP Basic (Recommended)` as the default option.  

    * `This skill's Connected Service requires intranet access to authenticate users (leave this unchecked if you are unsure).`  
        * Your app requires access to an intranet.  
    1. Request user profile data  

        ![Request user profile](../media/images/default_settings-request_user_profile_data-empty.png)

        * `Data`  
            * Click on the **Add a user profile request** link and select the user profile information from the drop-down menu.  
                Possible values are `user.info.email`  

                >[!TIP]
                > Repeat this step to select additional user profile data.  

                >[!IMPORTANT]
                > You are allowed to collect user profile data only to add to your Cortana Skill functionality.  

                ![Request user profile - all](../media/images/default_settings-request_user_profile_data-all.png)

    >[!TIP]
    > For more information about the bot configuration fields, visit the  [Connect a bot to Cortana](https://docs.microsoft.com/azure/bot-service/bot-service-channel-connect-cortana) page.  

1. Click on the **Deploy on Cortana** button.  

    >[!IMPORTANT]
    > The **Deploy on Cortana** button is enabled only after all of the required fields are completed.  
    > 
    > ![Back to Channels, Deploy on Cortana, Manage](../media/images/default_settings-back-deploy-manage.png) 

    ![Deploy on Cortana - enabled](../media/images/default_settings-back-deploy-manage-active.png)  

>[!NOTE]
> You may confirm your Cortana Skill is deployed on Bot Framework portal or Azure portal page using the same Microsoft account (MSA) that you registered in *Bot Framework* portal.

>[!TIP]
> For more information about testing your skill, visit the [Testing and Debugging Cortana Skills](./test-debug.md) page.  

## Test Group Settings  

Deploying to **Test Group** makes your Cortana Skill available to a group of users that you specify using individual MSA email addresses. Typically, you create a test group to have others test your Cortana Skill and provide feedback. Update your Cortana Skill before making generally available.  

1. On the *Configure Cortana* page, under the *Test Group Settings* section, enter the following information.  

    ![Test Group Settings - not configured](../media/images/test_group_settings-not_configured.png)  

    Complete the required fields that are marked with an asterisk (`*`).

    >[!NOTE]
    > For more information about the bot configuration fields, visit the [Connect a bot to Cortana](https://docs.microsoft.com/azure/bot-service/bot-service-channel-connect-cortana) page.  

    1. Skill information section  

        ![Skill information](../media/images/test_group_settings-skill_information.png)  

        * `Skill icon`  
            * Click on the **Upload icon** button and select an icon for your Cortana Skill.  
        * `Display name`  
            * >[!WARNING]
                > The value is limited to 30 characters.  
        * `Invocation name`  
            * >[!WARNING]
                > The value is not editable. 

    2. Request user profile data  

        ![Request user profile](../media/images/test_group_settings-request_user_profile_data-empty.png)

        * `Data`  
            * Click on the **Add a user profile request** link and select the user profile information from the drop-down menu.  
                Possible values are `user.info.email`  

                >[!TIP]
                > Repeat this step to select additional user profile data.  

                >[!IMPORTANT]
                > You are allowed to collect user profile data only to add to your Cortana Skill functionality.  

                ![Request user profile - all](../media/images/test_group_settings-request_user_profile_data-all.png)

    3. Group  
        ![MSA email addresses - empty](../media/images/test_group_settings-group-empty.png)  
        * `Member email`
            * Enter an MSA e-mail address, and then click Add.  

                >[!NOTE]
                > Use semicolons to separate multiple MSA e-mail addresses.  

                ![MSA email addresses](../media/images/test_group_settings-group-contoso_hotmail.png)

2. Click on the **Create Group** button.  

    >[!IMPORTANT]
    > The **Create Group** button is enabled only after all of the required fields are completed.  
    >
    > ![Back to Channels, Create Group](../media/images/test_group_settings-back-create.png)  

    ![Create Group - enabled](../media/images/test_group_settings-back-create-active.png)

3. After your test group is created, the *Test Group Settings* section displays the following changes.  

    * Group  

        ![Group - created](../media/images/test_group_settings-group-contoso_hotmail-group_access_url.png)  

        * `Member email`

        * `Group Access URL`  
            * >[!IMPORTANT]
                > You must manually send an email message to the designated MSA users listed in the `Data` field. The email message must include the `Group Access URL`.  
                >
                > When an MSA user receives the **Group Access URL** from you, the user has the option to **Accept** or **Decline** joining the skill test group. If the user accepts joining the skill test group, then access is granted to test your Cortana Skill. If the user declines joining the test group, then access is denied to test your Cortana Skill.  

    * The **Reset Group** Button is added and the **Create Group** button is replaced by the **Save changes** button.  

        ![Reset Group, Back to Channels, Save changes](../media/images/test_group_settings-reset-back-save.png)

    * The **Test Group Setting** link is updated.  

        ![Test Group Settings - configured](../media/images/test_group_settings-configured.png)  

        >[!WARNING]
        > The **Reset Group** button removes all members of the group.  

>[!IMPORTANT]
> To avoid issues, remove all of the member of the group on promotion to *World*.  

## World Settings  

>[!IMPORTANT]
> You must complete the required fields before submitting your Cortana Skill for review.  
>
> >[!TIP]
> > If you complete some of the required fields and need to continue later, then click on the **Save and Close** button at the bottom. This enables you to preserve the fields you populated. You are able to resume the rest at a later time.  

Deploying your Cortana Skill to **World** published your Cortana Skill in all markets that you specified when you registered your bot.  

>[!IMPORTANT]
> Before publishing your Cortana Skill to **World**, read and comply with the Certification requirements.  
>
> >[!TIP]
> > For more information about the requirements for publishing to **World**, visit the [Cortana Skills Kit Certification Requirements](./skill-review-guidelines.md) page.  

1. On the *Configure Cortana* page, under the *World Settings* section, enter the following information.  

    ![World Settings - not configured](../media/images/world_settings-not_configured.png)  
    Complete the required fields that are marked with an asterisk (`*`).

    >[!NOTE]
    > For more information about the bot configuration fields, visit the [Connect a bot to Cortana](https://docs.microsoft.com/azure/bot-service/bot-service-channel-connect-cortana) page.  

    1. Skill information section  

        ![Skills information](../media/images/world_settings-skill_information.png)  

        * `Skill icon`  
            * Click on the **Upload icon** button and select an icon for your Cortana Skill.  
        * `Display name`  
            * >[!WARNING]
                > The value is limited to 30 characters.  
        * `Invocation name`  
            * >[!WARNING]
                > The value is not editable. 
        * `Short description`  
        * `Long description`  
        * `Sample Invocation Phrase`
            * Enter an invocation phrase and click on the **Add sample invocation phrase** button.  
        * `Primary category`  
            * Click the drop-down menu to select a category that matches your Cortana Skill.  
                Possible values are `developer tools`, `entertainment`, or `health & fitness`

                >[!NOTE]
                > Select a category to enable your Cortana Skill to be searched and discovered by your users.  
        * `Secondary category (Optional)`  
            * Click the drop-down menu to select a secondary category.  
        * `Tags`  
            * Enter a unique word and click on the Add button.  

                >[!NOTE]
                > You may create several more tags by repeating this step. The `Tags` field is similar to the `Primary category` and `Secondary category` fields enhancing the ability for your Cortana Skill to be searched and discovered by your users.  
        * `Supported platforms`  

    2. `Does this Cortana skill collect users' personal information?`  

        ![Does this Cortana skill collect users' personal information?](../media/images/world_settings-collect_users_information-off.png)  

        * Request user profile data

            ![Does this Cortana skill collect users' personal information?](../media/images/world_settings-collect_users_information-on.png)  

            * `User data`  
                * ![Does this Cortana skill collect users' personal information?](../media/images/world_settings-collect_users_information-on-user_data.png)  

            * `Additional User Data`  

    3. Developer Account section  

        ![Developer Account Type - Developer](../media/images/world_settings-developer_account-developer.png)  ![Developer Account Type - Company](../media/images/world_settings-developer_account-company.png)  

        * `Developer Account Type`  
            * Click on the radio button matching your type.  

                >[!TIP]
                > If you are an individual or student developer, then select `Developer`.  

                >[!TIP]
                > If you are part of a company, then select `Company`.  

    4. Developer Information section  

        ![Developer Information](../media/images/world_settings-developer_information.png)

        * `First name`              
        * `Last name`              
        * `Email`             
        * `Phone number`  
        * `Address 1` and `Address 2`  
        * `City/District`  
        * `State`  
        * `Zip code`  
        * `Country`  
        * `Developed by (for ISVs)`  
        * `Published by`  
        * `Developer or Company Website URL`  
    5. Support Contact section  

        ![Support Contact](../media/images/world_settings-support_contact.png)

        * `Email`  
        * `Website URL`  
    6. Publisher Information section  

        ![Publisher Information](../media/images/world_settings-publisher_information.png)

        * `Name`  
        * `Email`  
        * `Phone number`  
    7. Privacy policy and terms of use section  

        ![Privacy policy and terms of use](../media/images/world_settings-privacy_policy_terms_of_use.png)

        * `Privacy policy (URL)`  
        * `Terms of Use (URL)`  
        * `Notices`  
    8. Validation and testing instructions section  

        ![Validation and testing instructions](../media/images/world_settings-validation_testing_instructions.png)  

2. Click on the **Save** button.  

    >[!IMPORTANT]
    > The **Save** button is enabled only after all of the required fields are completed.  
    >
    > ![Back to Channels, Save, Submit for Review](../media/images/world_settings-back-save-submit.png)  

3. Click **Submit for review**.  

    >[!IMPORTANT]
    > The **Submit for review** button is enabled only after all of the required fields are completed.  
    >
    > ![Back to Channels, Save, Submit for Review](../media/images/world_settings-back-save-submit.png)

    ![Submit for Review - enabled](../media/images/world_settings-back-save-submit-active.png)

    >[!IMPORTANT]
    > After submission for review, you are not be able to edit the properties or delete your Cortana Skill.  

4. After submitting for review, the *World Settings* section displays the following changes.  

    * The **Save** button and **Submit for Review** button are removed.  

        ![Reset Group, Back to Channels, Save changes](../media/images/world_settings-back-submitted-approved.png)

    * The **World Setting** link is updated.  

        ![World Settings - configured](../media/images/world_settings-configured.png)

    >[!IMPORTANT]
    > A review status message that indicates the review status for your Cortana Skill by the Cortana Certification team. If the Cortana Certification team has any concerns or questions during the review process, then you receive an email message. You may refer to the *World Settings* section to verify acceptance state of your Cortana Skill. If rejected, then the details and reasons for rejection are provided. If all requirements are met, then your Cortana Skill is approved and deployed. In the *World Settings* section, the word `Approved` following by the approval date is displayed.

    >[!TIP]
    > If you encounter any technical issues and you require assistance, then please send an email message to [Cortana Skills Kit Support@microsoft.com](mailto:skillsup@microsoft.com).

    >[!TIP]
    > To read or post Cortana Skills Kit questions on Stackoverflow, visit the [Stackoverflow - Cortana Skills Kit Questions](https://stackoverflow.com/questions/tagged/cortana-skills-kit) page.  

### Withdraw Your Submission  

Your Cortana Skill is locked during submission review. If you want to make changes to your Cortana Skill, then click on the **Withdraw your submission**.  

>[!IMPORTANT]
> You may withdraw your Cortana Skill only during the following stages.  
> * Prior to start of review  
> * During review  
> * After approval, but prior to publishing to the **World**  
>
> All the properties entered in **World Settings** are saved. You may update the publishing properties of your Cortana Skill and resubmit for review and certification.  

### Common Reasons for Review Failure 

If you read and adhere to the [review requirements](./skill-review-guidelines.md), then you should pass the review.  
There are some common reasons why a Cortana Skill fails the review.  

* The invocation name does not meet policy requirements.  
* Your submission does not provide sample invocation phrase.  
    Provide at least three sample invocation phrases that demonstrate your Cortana Skill.  
    Ensure that the invocation phrases actually work.  
    Provide enough samples that demonstrate all key features.  
* You provide sample phrases with one or more of the following issues.
 
    * The phrase doesn't include a launch word (Ask, Tell, and so on) or an invocation name.  

        >[!TIP]
        > For a skill called **My Events**  
        > * `My Events update` : Missing the launch word.  
        > * `ask for an update` : Missing the invocation name.  

    * The samples do not work as expected or described.  

        >[!TIP]
        > If the invocation phrase is `Ask My Events to find a nearby event`, then your Cortana Skill should either return nearby event information or ask for more information.  

* The skill does not provide support for help. Most first-time users will ask the skill for help (usually by saying "Help"). If a user asks for help, then your skill must tell the user how to use the skill.
<br /><br />
For example, if your skill involved checking stock prices, your help could be "Please say the name of a stock. For example, say Microsoft."

* Your skill infringes on the intellectual property (IP) of another company.  
    The name and invocation name of your Cortana Skill should not consist of any trademarked or copyrighted words unless you have permission to do so from the owner.
    Ensure that you have the right to share the content that your skill provides.
<br /><br />
Ensure that your skill doesn't make use of any unlicensed or pirated audio or visual content.  

### Delete Channel  

Deleting a Cortana Skill involves deleting the channel inside the BotFramework portal.  To be able to delete the Cortana channel on a bot, the skill must not be published to **World**.  

If you need to delete a Cortana Skill that is published to **World**, then you must contact the Cortana Certification team. If a skill is under review by the Cortana Certification team, then you must first withdraw your submission before deleting the Cortana channel.  

1. On the *Configure Cortana* page, at the bottom of all sections, click **Delete Channel** button.  

    ![Delete Channel](../media/images/delete_channel.png)  
