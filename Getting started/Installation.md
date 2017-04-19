# Installation

In this guide, we will talk about the options to setup SlimGIS products on your machine. We provide two common ways. You can choose either one that you are already familiar with.

- Installer
- NuGet

Now we will talk the two options in detail one by one.

### Installer 

This is a traditional way to setup our products on a machine. To get the installer from [slimgis.com](http://www.slimgis.com) and follow the wizard to get everything ready. 

> During the installation, the msi file might be locked for the first time by the OS, please unlock it in msi file property dialog before executing the installer or run it anyway if you see the smartscreen window. If you think it is a risk to you, NuGet is proper for you.

By default, the files will be installed at *C:\Program Files (x86)\SlimGIS*. In this folder, we deployed the following things that are helpful for your project. 
- The SDK for all our components. Includes:
    - .NET
        - WPF ([version]\SDK\Wpf)
        - WinForms ([version]\SDK\WinForms)
        - WebAPI ([version]\SDK\WebApi)
        - Core ([version]\SDK\Core)
    - .NET Core
        - WebAPI ([version]\SDK\WebApi.Dnc)
        - Core ([version]\SDK\Core.Dnc)
- The documentation
    - The API reference links that are host on our server
    - A startup handbook PDF file to find some useful resources for beginner
- License Manager
    - Includes a CLI application to manage your licenses. View [this guide](https://github.com/SlimGIS/Start-up-Handbook/blob/master/LicenseTypeGuide.md) for more detail.
    

### NuGet

NuGet is a fashion way to manage your project references. We host our products to NuGet so that you can easily setup your project. 

> Because SlimGIS products are managed by [license](https://github.com/SlimGIS/Start-up-Handbook/blob/master/LicenseTypeGuide.md). We designed a temporary license that allows you to evaluate our components for 7 days without any limits. After that period, you still need to get a license to continue another 60 days period evaluation or purchase one. We hope you like it.

Open your NuGet Package Manager in Visual Studio (*Right click on your project Referecnes node in Solution Explorer -> Manage NuGet Packages...*); switch to the `browse` tab and input `SGMapKit` or `SlimGIS` in the search box, our products will list in the result.

There are two pattern for the package names. To understand it will help you to find the component quickly for your project.

- `SGMapKit.*` are all our major components. For example, to add reference to WPF project, select `SGMapKit.Wpf`.
- `SGMapKitEx.*` means the extensions that serves with the major components. Usually, those packages are built above SGMapKit.Core. There are several reasons that we build packages as extensions.
    - *Unstable* functions, they are not very stable, we might put them into our core in the future release. 
    - *Unmanaged or requires a 3rd party library*, we want to make our infrastructure simple, lite and portable; if this function prevents the preconditions, we will separate them apart.

That's all for this guide, if you need more information, please [contact us](mailto:support@slimgis.com).

Kind Regards,

SlimGIS Dev Team