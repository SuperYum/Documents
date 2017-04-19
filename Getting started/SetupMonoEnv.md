# Setup Mono Environment
1. Our guide is started from a clean Ubuntu OS 14.04 environment.

1. Open the terminal by pressing `Ctrl + Alt + T`.

1. Add the Mono Project GPG signing key and the package repository to your OS. Please issue flowing command line by line:

    ```perl
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
    
    echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list
    
    sudo apt-get update
    ```

1. Add the second repository to OS to install **mode_mono**

    ```perl
    echo "deb http://download.mono-project.com/repo/debian wheezy-apache24-compat main" | sudo tee -a /etc/apt/sources.list.d/mono-xamarin.list
    ```
    
1. Now we are going to install the mono environment. It might take a few minutes depending on the network.
    
    ```perl
    sudo apt-get install mono-devel

    sudo apt-get install mono-complete

    sudo apt-get install referenceassemblies-pcl
    ```
    
    > ***Note***: Please enter `Y` when asking if you want to continue.
    
1. At this step, the mono environment is prepared. We will install the IDE - MonoDevelop with the this command line.
    
    ```perl
    sudo apt-get install monodevelop=5.10.0.871-0xamarin2
    ```
    
    Another option is to install the normal build without the ASP.NET add-in support.
    
    ```perl
    sudo apt-get install monodevelop
    ```
    
1. If you want to host a web application, please install **XSP4**.
    
    ```perl
    sudo apt-get install mono-xsp4
    ```

Now, the Mono environment is setup and the IDE is also installed. Hope you enjoy creating apps with C# on Linux.

> This article refers to the official guide ***Install Mono on Linux***. Click [here](http://www.mono-project.com/docs/getting-started/install/linux/#debian-ubuntu-and-derivatives) to know more.
