# Office 365 Profile sample for Windows

**Table of contents**

* [Introduction](#introduction)
* [Prerequisites](#prerequisites)
* [Register and configure the app](#register)
* [Build and debug](#build)
* [NuGet packages used in the sample](#packages)
* [Questions and comments](#questions)
* [Additional resources](#additional-resources)

<a name="introduction"></a>
##Introduction

The Office 365 Profile sample for Windows uses the Office 365 unified endpoint (preview) to get user profile data from various services such as Active Directory, SharePoint, and OneDrive. 

The first page presents you with a list of users. The second page displays information about any user you choose to view. All of this information, including files shared with the user, the user's email address, hire date, manager, and direct reports, comes from the unified endpoint.

<a name="prerequisites"></a>
## Prerequisites ##

This sample requires the following:  
  * Visual Studio 2013 with Update 4.  
  * An Office 365 account. You can sign up for [an Office 365 Developer subscription](http://aka.ms/ro9c62) that includes the resources that you need to start building Office 365 apps.
  * A Microsoft Azure tenant to register your application. Azure Active Directory provides identity services that applications use for authentication and authorization. A trial subscription can be acquired here: [Microsoft Azure](http://aka.ms/jjm0q7).

**Important**: You will also need to ensure your Azure subscription is bound to your Office 365 tenant. To do this see the Active Directory team's blog post, [Creating and Managing Multiple Windows Azure Active Directories](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx). In this post, the *Adding a new directory* section will explain how to do this. You can also read [Set up your Office 365 development environment](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription) for more information.

<a name="register"></a>
##Register and configure the app

1.	Sign in to the [Azure Management Portal](http://aka.ms/i5b8dz), using your Azure AD credentials.
2.	Click **Active Directory** on the left menu, then select the directory for your Office 365 developer site.
3.	On the top menu, click **Applications**.
4.	Click **Add** from the bottom menu.
5.	On the **What do you want to do page**, click **Add an application my organization is developing**.
6.	On the **Tell us about your application page**, specify **O365-Win-Profile** for the application name and select **NATIVE CLIENT APPLICATION** for type.
7.	Click the arrow icon on the bottom-right corner of the page.
8.	On the **Application information** page, specify a **Redirect URI**, for this example, you can specify http://localhost/profileSample, and then select the checkbox in the lower-right hand corner of the page. Remember this value for the following **Build and debug** section.
9.	Once the application has been successfully added, you will be taken to the **Quick Start** page for the application. From here, select **Configure** in the top menu.
10.	Under **permissions to other applications**, select **Add application**. In the dialog box, select the **Office 365 unified API (preview)** application. After you return to the application configuration page, select the **Read items in all site collections**, **Read users' files**, and **Access directory as the signed in user** permissions.
11.	Copy the value specified for **Client ID** on the **Configure** page, and be sure to remember the value you specified for the redirect URI.
12.	Click **Save** in the bottom menu.

<a name="build"></a>
## Build and debug ##

**Note:** If you see any errors while installing packages during step 3 (for example, *Unable to find "Microsoft.IdentityModel.Clients.ActiveDirectory"*) make sure the local path where you placed the solution is not too long/deep. Moving the solution closer to the root of your drive resolves this issue.

1. After you've loaded the solution in Visual Studio, configure the sample to use the client id that you registered in Azure Active directory by adding the following key and its corresponding value to the Application.Resources node of the App.xaml file.
![Office 365 Profile sample](/readme-images/ClientId.png "Client ID value in App.xaml file")`


2. Open the AuthenticationHelper.cs file and set your redirect URI as the value of this variable.
![Office 365 Profile sample](/readme-images/RedirectUri.png "Redirect URI value in AuthenticationHelper.cs file")`

3. Press F5 to build and debug. Run the solution and sign in with your organizational account to Office 365.

<a name="packages"></a>
## NuGet packages used in the sample ##

The NuGet packages used in this sample will load automatically when you build the solution. If you want to create an app that uses the unified endpoint, be sure to install the following packages:

1. [Microsoft.IdentityModel.Clients.ActiveDirectory v.2.14](http://aka.ms/rmclss)
2. [Office 365 unified API client library (preview)](https://www.nuget.org/packages/Microsoft.Graph/)
3. [Microsoft.OData.ProxyExtensions v1.0.30](https://www.nuget.org/packages/Microsoft.OData.ProxyExtensions/)

<a name="questions"></a>
##Questions and comments##

- If you have any trouble running this sample, please [log an issue](https://github.com/OfficeDev/O365-Win-Profile/issues).
- For more general feedback, send and email to [docthis@microsoft.com](mailto:docthis@microsoft.com?subject=Feedback%20on%20the%20Office%20365%20Windows%20unified%20endpoint%20app).

<a name="additional-resources"></a>
## Additional resources ##

- [Office 365 profile sample for Android](https://github.com/OfficeDev/O365-Android-Profile/)
- [Office 365 profile sample for iOS](https://github.com/OfficeDev/O365-iOS-Profile/)
- [Office 365 unified API overview (preview)](https://msdn.microsoft.com/en-us/office/office365/howto/office-365-unified-api-overview)
- [Office 365 APIs platform overview](https://msdn.microsoft.com/office/office365/howto/platform-development-overview)
- [Office 365 API code samples and videos](https://msdn.microsoft.com/office/office365/howto/starter-projects-and-code-samples)
- [Office developer code samples](http://dev.office.com/code-samples)
- [Office dev center](http://dev.office.com/)
- [Connecting to Office 365 in Windows Store, Phone, and universal apps](https://github.com/OfficeDev/O365-Win-Connect)
- [Office 365 Code Snippets for Windows](https://github.com/OfficeDev/O365-Win-Snippets)
- [Office 365 Starter Project for Windows Store App](https://github.com/OfficeDev/O365-Windows-Start)
- [Office 365 REST API Explorer for Sites](https://github.com/OfficeDev/Office-365-REST-API-Explorer)

## Copyright
Copyright (c) 2015 Microsoft. All rights reserved.