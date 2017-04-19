# Ways to add MapKit References

SlimGIS MapKit Dev Team provides various ways to add necessary MapKit references into your project. You could choose either one that you already familiar with. Let's take a look at them.

### Reference by assemblies
This is the original way that every developer must be familiar with. Before adding the reference, we must get SlimGIS MapKit assemblies ready on your machine. We could get SlimGIS installer or download the assembly package in the dashboard of [our website](http://www.slimgis.com).

When the assemblies are prepared on your machine, let's create a project with Visual Studio. Then on the solution explorer -> right click on the _References_ folder -> select _Add Reference..._. 
- If you are using SlimGIS installer, the default SDK folder is placed at: _C:\Program Files (x86)\SlimGIS\3.0.0\SDK\[specific component folder]_.
- If you download the assembly package manually, please extract it anywhere on your computer and target the assemblies there.

### Reference by NuGet
We keep updating our stable build and preview build into NuGet.org so that developers could maintain the packages easier with NuGet manager. Recently, more and more developers are used to manage their references with NuGet. 

To use NuGet, we don't need to download the installer nor download the assembly package manually. What we need to do is only open Visual Studio -> create a project -> right click on the _References_ folder -> select _Manage NuGet Packages..._ -> _NuGet View_ will add into the work area -> switch the tab to _Browse_ (sometimes, the default active tab is _Installed_) -> in the search box, type `sgmapkit` -> our packages will be in the result list.

![nuget result](https://github.com/SlimGIS/Documents/raw/master/Images/nuget-package-search-result.png)

With NuGet, you could easily add / remove / upgrade our packages in your project. It is pretty straight forward right? I really love this way :)

### Reference by project template
We prepared a easest way to setup a very simple map based app project on your machine. With the strength of Visual Studio, we can install our online project template. Follow my steps to get the project template setup on your machine.

Open Visual Studio -> click _Tools_ in the menu bar -> select _Extensions and Updates..._ -> select _Online_ node on the left side panel -> search `slimgis` and our project template will be in the result list.

![online project template result](https://github.com/SlimGIS/Documents/raw/master/Images/online-project-template.png)

Once it is installed, restart Visual Studio, then create a new project, our project template will be in the bottom of the installed project template.

![installed project template](https://github.com/SlimGIS/Documents/raw/master/Images/proj-template-ready.png)

Here we introduced several ways to add MapKit assemblies into your project. 
- A normal way that developers are already familiar with
- A fasion way that easier to manage the reference's adding/removing/updating
- A pre-defined project template that to quickly kick starts your map app project

Hope you like it. Any suggestion is welcome to send to dev@slimgis.com. 