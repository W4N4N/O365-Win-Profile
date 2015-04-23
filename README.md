# Office 365 Profile Sample for Windows

**Table of contents**

* [Introduction](#introduction)
* [Prerequisites](#prerequisites)
* [Register and configure the app](#register)
* [Build and debug](#build)
* [NuGet packages used in the sample](#packages)
* [Questions and comments](#questions)
* [Next steps](#next-steps)
* [Additional resources](#additional-resources)

<a name="introduction"></a>
##Introduction

The Office 365 Windows Profile sample uses the **Office 365 unified endpoint (preview)** to fetch user profile data from various services such as Active Directory, SharePoint, Exchange, and OneDrive. 

The first page presents you with a list of users. The second page displays information about any user you choose to view. All of this information, including files shared with the user, the user's email address, hire date, manager, and direct reports, comes from the unified endpoint.

<a name="prerequisites"></a>
## Prerequisites ##

This sample requires the following:  
  - Visual Studio 2013 with Update 3.  
  - [Office 365 API Tools version 1.3.41104.1](http://aka.ms/k0534n).  
  - An Office 365 account. You can sign up for [an Office 365 Developer subscription](http://aka.ms/ro9c62) that includes the resources that you need to start building Office 365 apps.
  - A Microsoft Azure tenant to register your application. Azure Active Directory provides identity services that applications use for authentication and authorization. A trial subscription can be acquired here: [Microsoft Azure](http://aka.ms/jjm0q7).

**Important**: You will also need to ensure your Azure subscription is bound to your Office 365 tenant. To do this see the Active Directory team's blog post, [Creating and Managing Multiple Windows Azure Active Directories](http://aka.ms/lrb3ln). The section **Adding a new directory** will explain how to do this. You can also read [Set up Azure Active Directory access for your Developer Site](http://aka.ms/fv273q) for more information.

<a name="register"></a>
##Register and configure the app

1.	Sign in to the [Azure Management Portal](http://aka.ms/i5b8dz), using your Azure AD credentials.
2.	Click **Active Directory** on the left menu, then select the directory for your Office 365 developer site.
3.	On the top menu, click **Applications**.
4.	Click **Add** from the bottom menu.
5.	On the **What do you want to do page**, click **Add an application my organization is developing**.
6.	On the **Tell us about your application page**, specify **O365-Win-Profile** for the application name and select **NATIVE CLIENT APPLICATION** for type.
7.	Click the arrow icon on the bottom-right corner of the page.
8.	On the **Application information** page, specify a **Redirect URI**, for this example, you can specify http://localhost/profileSample, and then select the checkbox in the lower-right hand corner of the page. Remember this value for the below section **Getting the ClientID and RedirectUri into the project**.
9.	Once the application has been successfully added, you will be taken to the **Quick Start** page for the application. From here, select **Configure** in the top menu.
10.	Under **permissions to other applications**, add the **Office 365 unified API (preview)** application, and select the **Read all users' basic profiles** permission.
11.	Copy the value specified for **Client ID** on the **Configure** page, and be sure to remember the value you specified for the redirect URI.
12.	Click **Save** in the bottom menu.

<a name="build"></a>
## Build and debug ##

1. After you've loaded the solution in Visual Studio, configure the sample to use your client id by adding the following keys and their corresponding values to the App.xaml file inside the O365-Win-Profile project:

        <x:String x:Key="ida:ClientID"><your client id></x:String>
        <x:String x:Key="ida:AuthorizationUri">https://login.microsoftonline.com</x:String>

2. Open the AuthenticationHelper.cs file and set your redirect URI as the value of this variable:
`private static Uri redirectUri = new Uri("https://<your redirect URI>");`

3. Press F5 to build and debug. Run the solution and sign in with your organizational account to Office 365.

<a name="packages"></a>
## NuGet packages used in the sample ##

The NuGet packages used in this sample will load automatically when you build the solution. If you want to create an app that uses the unified endpoint from scratch, be sure to install the following packages:

1. [Microsoft.IdentityModel.Clients.ActiveDirectory v.2.14](http://aka.ms/rmclss)
2. Microsoft.Graph
3. Microsoft.OData.ProxyExtensions v1.0.30

<a name="questions"></a>
##Questions and comments##

- If you have any trouble running this sample, please [log an issue](https://github.com/OfficeDev/O365-Win-Profile/issues).
- For more general feedback, send and email to [docthis@microsoft.com](mailto:docthis@microsoft.com?subject=Feedback%20on%20the%20Office%20365%20Windows%20unified%20endpoint%20app).

<a name="additional-resources"></a>
## Additional resources ##

- [Office 365 APIs documentation](http://aka.ms/kbwa5c)
- [Office 365 APIs starter projects and code samples](http://aka.ms/x1kpnz)
- [Office developer code samples](http://aka.ms/afh45z)
- [Office dev center](http://aka.ms/uftrm1)
