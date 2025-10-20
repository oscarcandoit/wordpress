---
url: https://wordpress.org/documentation/article/tools-export-personal-data-screen
scraped_at: 2025-10-20T02:02:56.254Z
---

[Skip to content](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Tools Export Personal Data screen

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Tools Export Personal Data screen

Search documentation

# Tools Export Personal Data screen

## In this article

Table of Contents

- [Using Export Personal Data](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#using-export-personal-data)
  - [Basic Usage](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#basic-usage)
  - [Downloading Personal Data](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#downloading-personal-data)
  - [Filtering Request](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#filtering-request)
  - [Resending the mail](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#resending-the-mail)
  - [Removing Request](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#removing-request)
- [Exported Personal Data](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#exported-personal-data)

[↑ Back to top](https://wordpress.org/documentation/article/tools-export-personal-data-screen/#wp--skip-link--target)

WordPress 4.9.6 included a feature to archive user data for export. Export Personal Data tool can generate a ( `.zip` format) file containing the personal data which exists about a user within your WordPress site.

Note: As this tool ONLY gathers data from WordPress and
participating plugins, you may need to go beyond to comply with export
requests.

## [Using Export Personal Data](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#using-export-personal-data)

### [Basic Usage](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#basic-usage)

Export Personal Data tool uses email validation to send a user’s request to an administrator.

1\. Select **Tools** -\> **Export Personal Data** from Administration Screens.

[![](https://i0.wp.com/wordpress.org/documentation/files/2019/02/ExportPersonalData_4.9.6-1.jpg?fit=1083%2C603&ssl=1)](https://wordpress.org/support/?attachment_id=11158276) Export Personal Data Screen

2\. Specify Username or email address and click **Send Request**.

If Confirmation request initiated successfully, the request will be shown in below Requester Table and **Status** will be changed to _Pending_.

[![](https://i2.wp.com/wordpress.org/documentation/files/2019/02/ExportPersonalData_4.9.6_pending.jpg?fit=879%2C260&ssl=1)](https://wordpress.org/support/exportpersonaldata_4-9-6_pending/) Export Personal Data Pending Screen

User will receive the following mail with subject ‘\[<site\_name>\] Confirm Action: Extract Personal Data’.

```
Howdy,

A request has been made to perform the following action on your account:

     Export Personal Data

To confirm this, please click on the following link:
https://<site_address>/wp-login.php?action=confirmaction&request_id=94&confirm_key=99rqZB4CcRct8JwL55Ov

You can safely ignore and delete this email if you do not want to
take this action.

This email has been sent to atachibana@unofficialtokyo.com.

Regards,
All at <site_name>
http://<site_address>/

```

3\. If user click link in the mail, below page is shown.

[![](https://i0.wp.com/wordpress.org/documentation/files/2019/02/ExportPersonalData_4.9.6_confirmation.jpg?fit=370%2C377&ssl=1)](https://wordpress.org/support/exportpersonaldata_4-9-6_confirmation/)

At the same time, the Status of Request will be changed to _Confirmed_, and **Next Steps** shows **Email Data** button.

[![](https://i0.wp.com/wordpress.org/documentation/files/2019/02/ExportPersonalData_4.9.6_confirmed.jpg?fit=878%2C252&ssl=1)](https://wordpress.org/support/exportpersonaldata_4-9-6_confirmed/) Export Personal Data Confirmed Screen

4\. Click **Email Data**.

**Next Steps** will be changed to **Email Sent**.

[![](https://i2.wp.com/wordpress.org/documentation/files/2019/02/ExportPersonalData_4.9.6_confirmed-1.jpg?fit=878%2C252&ssl=1)](https://wordpress.org/support/exportpersonaldata_4-9-6_confirmed-2/)

User will receive following mail with subject ‘\[<site\_name>\] Personal Data Export’.

```
Howdy,

Your request for an export of personal data has been completed. You may
download your personal data by clicking on the link below. For privacy
and security, we will automatically delete the file on <expired_date>,
so please download it before then.

https://<site_address>/wp-content/uploads/sites/3/wp-personal-data-exports/wp-personal-data-file-atachibana-at-unofficialtokyo-com-TONWbmz8GqwFi5ScUBTrClel0zc4DkU0.zip

This email has been sent to atachibana@unofficialtokyo.com.

Regards,
All at <site_name>
http://<site_address>

```

**Note:** Link is available only 48 hours.

5\. If user click the link, `.zip` file will be downloaded that includes one index.html file. For detail format, refer below section Exported Personal Data.

At the same time, the **Status** of Request will be changed to _Completed_, and **Next Steps** displays **Remove request** button.

[![ExportPersonalData 4.9.6 completed.jpg](https://codex.wordpress.org/images/thumb/c/ca/ExportPersonalData_4.9.6_completed.jpg/600px-ExportPersonalData_4.9.6_completed.jpg)](https://codex.wordpress.org/images/thumb/c/ca/ExportPersonalData_4.9.6_completed.jpg/600px-ExportPersonalData_4.9.6_completed.jpg)

6\. Click **Remove request**. The request will be removed.

Note: There are no ‘Trash’ status such as Posts’.

### [Downloading Personal Data](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#downloading-personal-data)

You can download Personal Data from popup menu **Download Personal Data**.

1. Move mouse cursor on the Requester’s mail address in the Requester Table. **Download Personal Data** will be displayed.
2. Click **Download Personal Data**.

[![ExportPersonalData 4.9.6 download.jpg](https://codex.wordpress.org/images/thumb/0/09/ExportPersonalData_4.9.6_download.jpg/600px-ExportPersonalData_4.9.6_download.jpg)](https://codex.wordpress.org/images/thumb/0/09/ExportPersonalData_4.9.6_download.jpg/600px-ExportPersonalData_4.9.6_download.jpg)

`.zip` file will be downloaded that includes one index.html file. For detail format, refer below section Exported Personal Data.

At the same time, the Status of Request will be changed to _Completed_, and **Next Steps** shows **Remove request** button.

Note: Even in the _Pending_ status, you can download the Personal Data.

### [Filtering Request](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#filtering-request)

You can filter requests by Status or Requester’s mail address.

To Filter by Status

- Click **All**, **Pending**, **Confirmed**, **Failed** and **Completed** above Requester Table.

To Filter by Requester’s email address

- Insert full or part of email address in the box above Requester Table, and Click **Search Results**.

### [Resending the mail](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#resending-the-mail)

1. Select checkbox of the Request that you want to resend the mail.
2. Select **Resend email** from **Bulk Actions** dropdown box and click **Apply**.

### [Removing Request](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#removing-request)

1. Select checkbox of the Request that you want to remove.
2. Select **Remove** from **Bulk Actions** dropdown box and click **Apply**.

## [Exported Personal Data](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#exported-personal-data)

In the `.zip` file, one `index.html` file exists. To see the data double click the icon from Explorer (Windows) or Finder (Mac).

[![](https://i1.wp.com/wordpress.org/documentation/files/2019/02/ExportPersonalData_4.9.6_indexhtml.jpg?fit=994%2C526&ssl=1)](https://wordpress.org/support/exportpersonaldata_4-9-6_indexhtml/)

Export Personal Data tool only exports data from WordPress and participating plugins.
From WordPress, following data are exported as Personal Data:

- About WordPress site
- User Information
- Comments
- Media

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/tools-export-personal-data-screen/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Ftools-export-personal-data-screen%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

February 4, 2019

Last updated

June 8, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.