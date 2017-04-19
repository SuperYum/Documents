# License Options

Welcome to use SlimGIS MapKit Components. The components are protected with licenses. The purpose of this guide is to help to setup license CLI (a command line utility to view and generate license) and show you the license types we have. Hope it could help you to choose a proper license for your project.

### Setup License CLI
SlimGIS License CLI is a command line utility to manage our component license usage of your SlimGIS account. There are two entries to get this CLI.
- Download installer from slimgis.com, the CLI will be installed along with the installation. It is also added to PATH environment so that you could easily call this CLI anywhere in the command window. It's pretty convenient.
- If you don't want to use the installer, or you are in some other OS like Linux or macOS, it is optionally another way, download the CLI package [here](#), extract anywhere in your disk. You could decide whether to add to the PATH environment.

Here are some common command you could try before activating your license.
- View help to get all support commands: `sglic --help`
- Login: `sglic login -u USERNAME -p PASSWORD`
    > Once you login with this command line, your account is not required when you call the other commands unless you call logout command; or the login status expires after 24 hours. We also support attaching your account behind the command you are calling if you don't want to login. e.g. `sglic status -u USERNAME -p PASSWORD`.
- View current license status: `sglic status`
- Logout and clean the login caches: `sglic logout`

When you get those things ready, we are going to introduce the license types we have.

#### Temporary License  
This license is for developer who uses SlimGis MapKit Components for the first time.
You don't need to do anything to generate this license. We call it "_temporary_", for it has `7 days` temporary free trail period. After it is expired, you MUST register a SlimGIS account in [our website](http://www.slimgis.com) and activate the trial with SlimGIS License Command Line to get another 60 days trail period. 

#### Trail License
When you have SlimGIS account, you are ready to have 60 days free trail period for all our components. With trial license, you have full function of our components. But some limits visually. Like watermark, or a message popups up occasionally etc. That's according to the components' strategy. After the trail period is expired, there is a chance to extend the trial period. We are not that strict for the verification, please feel free to [contact us](mailto:support@slimgis) and tell us your situation.

To start trail for a product, for example WPF:
```perl
sglic start-trial wpf
```

Here is a list for the short name for our components, which makes easier to type and remember in CLI.

abbr.   |Full name
---     |---
core    |MapKit Core
wpf     |MapKit WPF
winforms|MapKit WinForms
webapi  |MapKit WebAPI
core-dnc|MapKit Core for .NET Core
webapi-dnc|MapKit WebAPI for ASP.NET Core

#### Full License
*Full License* is a purchased license. Each *Full License* can only bind to one machine for single developer.
With *Full License*, you could develop with full featured SlimGIS MapKit Component without any limits. The Full license is pepetual license. You could use it forever. The purchase of this license also comes with one year subscription, which means you are free to upgrade our component in one years. If you want to upgrade the next year, a new subscription must be purchased.

To activate a purchased license, for example WPF:
```perl
sglic activate wpf
```

Each license can be deployed on one machine. If you want to switch the development machine, please deactivate it with following command first and activate it on another machine.
```perl
sglic deactivate wpf
```

#### Runtime License
This license means the license for authorizing to run your application on another machine that doesn't have *full license*.

To generate a runtime license, for example a WPF application executable is `helloworld.exe`:
```perl
sglic runtime "[FOLDER]/helloworld.exe" -P wpf
```
> Note: the `-P` is upper case. This command generates a runtime license `helloworld.lic` in the same folder of the executable. You could also specify an output folder with an extra option `-o [OUTPUT FOLDER]`

Now, we have got our runtime license. You could simply pack the runtime license with the executable and it is ready to ship your app.

We also provide **another way to ship your app without the runtime license file**. It is good to make your application folder clean. Please follow a few steps: 
1. Open the generated runtime license file with text editor, copy the content in clipboard. 
2. Open your project properties.cs file. Add following attribute in the end of the file.
```csharp
[assembly:RuntimLicenseKey("[RUNTIME LICENSE CONTENT]")]
```
3. Rebuild the app and it is ready to ship without the runtime license file.

This command also compatible with Web applications. Instead of the executable, please set the full path of the DLL.

#### Offline Activation
1. Prepare a request file that is generated by [SlimGIS License CLI utility](https://github.com/SlimGIS/Start-up-Handbook/blob/master/LicenseGuide.md). For example, to generate a request file for WPF with `sglic offline-request wpf -o [OUTPUT PATH]`
4. Send a email with the request file as attachment to sales@slimgis.com.
5. We will check your request file and will send you back a registration file within 24 hours.
6. Then register the license with: `sglic offline-register -f [REGISTRATION FILE PATH]`
7. The license is successfully registered on your machine.

### The END
That's all about SlimGIS license. Hope it helps you to choose a proper license for your development. 
Also, we are glad to hear any suggestions from you to improve this guide. Please feel free to feedback us by [support@slimgis.com](mailto:support@slimgis.com).
