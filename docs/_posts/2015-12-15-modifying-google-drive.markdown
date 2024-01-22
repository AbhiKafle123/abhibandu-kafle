---
layout: default
title:  "Modifying/Deleting google drive files"
author: Abhibandu Kafle
date:   2015-12-15 18:29:40 -0500
tags: uncategorized
---
This is a short write up of a bug in OAuth 2.0 implementation of Google API.

This bug could have allowed an application to delete/write on user's any of the file(s) in google drive, although the user permitted the application to access only those files that were created by the application.

For an instance, an application requiring access to files created by itself looks like:

![oauthFlaw]({{ site.baseurl }}/assets/images/oauthFlaw.jpg)

According to [google API documentation](https://developers.google.com/drive/v2/reference/permissions), after the user clicks allow, the app should **only** be able to access files that was opened/created using this app.

I went ahead and tried deleting a file that *was in the user's drive* but wasn't ever accessed/created by the application. Following is the request I sent to test this:

`DELETE https://www.googleapis.com/drive/v2/files/fileId/permissions/permissionId`

The response was 204 No content. I checked the file in my drive, the file was no longer there.

This meant **any application that had drive.file permission(i.e the permission to see only those files that were created by the app itself) could have been abused to access private files of user. Not only this allowed an attack to read all the files on your drive, but also an attacker could modify/delete those files.** This was reported to google security team and has been fixed as of now.

Jun 5, 2015 - Reported.
Jun 5, 2015 - Triaged.
Jun 11, 2015 - Additional details sent.
June 26, 2015 - Fix confirmation, 1337$ bounty awarded.

Update: After Google fixed this issue, I was able to bypass the fix again. The bypass involved getting 'drive.readonly' permission along with 'drive.file' permission. 'drive.readonly' permission made everything in the user's Google drive visible to the application and 'drive.file' could still be used to delete/modify otheer files in user's Google drive.

The bypass has also been fixed by Google security team.