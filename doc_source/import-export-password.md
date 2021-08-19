# Using a password when importing or exporting<a name="import-export-password"></a>

Amazon Lex can password protect your export archives or read your protected import archvies using standard \.zip file compression\. You should always password protect your import and export archives\.

Amazon Lex sends your export archive to an S3 bucket, and it is available to you with a pre\-signed S3 URL\. The URL is only available for five minutes\. The archive is available to anyone with access to the download URL\. To help protect the data in the archive, provide a password when you export the bot or bot locale\. If you need to get the archive after the URL expires, you can use the console or the `DescribeExport` operation to get a new URL\.

If you lose the password for an export archive, you can create a new password for an existing file by choosing **Download** from the import/export history table or by using the `UpdateExport` operation\. If you choose **Download** in the history table for an export and you don't provide a password, Amazon Lex downloads an unprotected zip file\.