---
title: Known Issues for the Tableau Extensions API
layout: docs
--- 

The following section describes some issues in the current release of the Extensions API where the API or the platform does not behave as expected.  

For information about what is new or has changed in each release, see the [Release Notes for the Tableau Extensions API]({{ site.baseurl }}/docs/trex_release-notes.html)

**In this section**

* TOC
{:toc}


### Unable to print or save image of the extension in a dashboard

- If you print a dashboard to a `.pdf` file, or save the dashboard as an image (or receive an image of the dashboard, as part of subscription) the zone that contains the extension will be blank.

### HTML drop-down menus in popup dialog windows

- HTML drop-down menus in popup dialog windows do not work as expected on MacOS. Users will not be able to select menu items using the mouse. They can select items with the cursor keys. To avoid issues on MacOS, use radio buttons or another method for user selection in the popup dialog. 

### Decimal separators in parameters
- Decimal separators in parameters are not handled as expected for some locales. If your operating system locale uses commas for decimal separators, the `parameter.changeValueAsync` function expects a string that uses a comma as the decimal separator; however, the `parameter.currentValue` function will return a string using a period as the decimal separator, regardless of locale settings. 

### Full data access and permission errors 
When an extension needs full data access and the user does not have full data permission on the workbook, Tableau currently allows the extension to run. However, Tableau will throw a console error when the extension calls `getUnderlyingData()` method. See [Handle full data access and permission errors]({{ site.baseurl }}/docs/trex_getdata.html#handle-full-data-access-and-permission-errors).