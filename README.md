# Step by step sofa installation for developpers

This tutorial is made from a fresh ubuntu 17.10 install with nvidia drivers.

# Sofa's depencies installation + QtCreator (IDE)

For the beginning just run those lines. They come from the sofa installation guide : 
https://www.sofa-framework.org/community/doc/getting-started/build/linux/

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install build-essential
sudo apt-get install cmake cmake-qt-gui
sudo apt-get install ninja-build
sudo apt-get install clang
sudo apt-get install ccache
```

Now we will install the QT dependencies + the QtCreator (IDE). Go on : https://www.qt.io/download and download the opensource runnable.

Go in your download directory and run it.

```bash
cd ~/Downloads
sudo chmod +x qt-unified-linux-x64-3.0.2-online.run 
sudo ./qt-unified-linux-x64-3.0.2-online.run
```

Click skip, next, next ... And you should have this installation directory /opt/qt. Otherwise, check than you run it as root (sudo)

![screen1](../images/screen1.png)

Click next, next ... and you should face this page. 

![screen2](../images/screen2.png)

Please select the GCC version of the latest stable qt release. In this case QT 5.10 (~1,2 gb). You can select multiples compilers but for sofa it's useless and the download size will be bigger.

Let's finish the installation of sofa's dependencies, run those lines :

```bash
cd ~/
sudo apt-get install libboost-atomic-dev libboost-chrono-dev libboost-date-time-dev libboost-filesystem-dev libboost-locale-dev libboost-regex-dev libboost-system-dev libboost-thread-dev libboost-program-options-dev
sudo apt-get install python2.7-dev python-numpy python-scipy
sudo apt-get install libxml2-dev libcgal-dev libblas-dev liblapack-dev libsuitesparse-dev libassimp-dev
sudo apt-get install git
```

Now we will create a SOFA directory. This gonna be the place where we will have sources and builds.

```bash
cd ~/
mkdir SOFA
cd SOFA
```

Then download the master branch of sofa (quite stable).

```bash
git clone -b master https://github.com/sofa-framework/sofa ./sofaSrc
```

When the download is finished run QtCreator. If you have multiples qtcreator installation, please ensure it's the QtCreator community.

![screen3](../images/screen3.png)

Click on "Open project"

![screen4](../images/screen4.png)

Go in SOFA directory, then sofaSrc (sofa sources) and select CMakeLists.txt

![screen5](../images/screen5.png)

Click on configure project. If you are curious the defaut build kit should be the gcc/qt version we downloaded from the qt installer.

![screen6](../images/screen6.png)

The cmake from QtCreator will run by itself. Then you will be able to compile sofa. Now it's cofee time (~20 mins depending of your machine)

![screen7](../images/screen7.png)

The compilation step should works withtout any problems. If you encounter some issue, please go on gitter for helps : gitter.im/sofa-framework/sofa
You can also use the sofa forum (maybe longer than using gitter) : https://www.sofa-framework.org/community/forum/

If everything works well you will be able to run it and discover sofa :D
Do not forget to select runSofa. Which is the main runnable of Sofa
![screen8](../images/screen8.png)
![screen8](../images/screen9.png)

Few explanations, the sofa source dir is sofaSrc. With the compilation, a new directory may be created. Something like build-sofaSrcXXXXXXXXXXXXXXXXXXXXXX. This is the build directory. If you explore it, you will find sofa's runnable inside the bin directory.

![screen10](../images/screen10.png)

