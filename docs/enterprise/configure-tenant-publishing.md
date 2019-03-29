---
title: Configure tenant publishing
description: Configuring the publishing process for enterprise skills.

ms.author: v-daturc
ms.date: 03/29/2019
ms.topic: article

keywords: cortana, enterprise, skills
---

# Configure tenant publishing

Once the skill is ready to be published, skill developers must complete the required fields on the **Tenant Publishing** tab.

The fields in the form that are marked with asterisks are required. Many fields (like name and address) are self-explanatory, and will not be described here. Fields that may not be as clear will be described below.

## Skill information

![Tenant publishing screenshot](../media/images/TenantPub-08.png)

- Display Name - Unique name that Cortana presents to the end user. Displayed in Directory and on Cortana's Canvas.
- Invocation Name (required) - Add a descriptive invocation name following the [Cortana Invocation Guidelines](https://docs.microsoft.com/en-us/cortana/skills/cortana-invocation-guidelines).
- Short description (required) - This description will show up in Cortana's Notebook.
- Long description (required) - This will be used as part of the certification process.
- Sample Invocation Phrase (required) - At least 3 examples, for example, "Ask Outlook to show my urgent messages".
- Primary category (required) - For example, `Utilities and tools`, `Productivity`, `Developer Tools`, etc. (The full list is on the [List of Cortana categories for publishing](./cortana-categories-for-publishing.md) page.)
- Secondary category (optional)
- Tags (optional) - You can ignore this field. Tags are used for consumer skills, not enterprise skills.
- Supported platforms (required) - For enterprise skills, choose Windows 10.

## Developer Account

![Tenant publishing screenshot](../media/images/TenantPub-09.png)

In general, you should select `Developer` for skills developed by a particular person or team, and `Company` for enterprise skills, but your choice will make no difference in how you fill out the rest of this form.

## Developer Information

![Tenant publishing screenshot](../media/images/TenantPub-07.png)

- First name (required) - First Name of AAD owner.
- Last name (required) - Last Name of AAD account owner.
- Country (required) - Two-character country code. (For example, US, UK, CA, CN).
- Developed by (for ISVs) - Name of the person who developed the skill (if different from above).
- Published by - Name of the developer, team, or company who developed the skill.
- Developer or company website URL - Developer’s or team’s website. May be the same as the **Support contact** URL below.

## Support Contact

![Tenant publishing screenshot](../media/images/TenantPub-06.png)

- Provide at least one method of communication: email, website, or both.
- Email - Support email.
- Website URL - Support website or company’s website.

## Publisher information

![Tenant publishing screenshot](../media/images/TenantPub-05.png)

- Name - This could be the name of the person, company, or team that developed the skill, but should be whoever will be providing support for the skill.
- Email - Support contact (can be the same as the email listed in **Support Contact** above).
- Phone number - Support number, preferably with country code, area code, prefix, and line number.

## Privacy policy and terms of use

![Tenant publishing screenshot](../media/images/TenantPub-04.png)

You must have both a Privacy Policy and Terms of Use for your skills, and they must be available online.

## Validation and testing instructions

![Tenant publishing screenshot](../media/images/TenantPub-01.png)

This information will help your IT Admins with the approval process. Your enterprise may have established guidelines as to what should be in this field. In general, though, it's better to include too much information than not enough.

## Deployment Configuration

![Tenant publishing screenshot](../media/images/TenantPub-03.png)

- Deploy to entire tenant – publishes the skill to everyone in the enterprise.
- Deploy to security groups – publishes the enterprise skill only to members of the associated security groups

>[!NOTE]
>In order for security groups to work, Cortana must be added as a service principal in your tenant by an IT administrator. See [Adding Cortana as a service principal](enterprise-cortana-service-principal.md).

![Tenant publishing screenshot](../media/images/TenantPub-02.png)

Once you've filled in all the required fields on the page, click `Submit for Review` to send the skill off to your IT Administrators for certification. Alternatively, you can save this information at any point by pressing the `Save` button. If you do, then you can return to the page and edit it at any time until you submit it for certification and publishing. Once it's submitted, the skill configuration cannot be changed.