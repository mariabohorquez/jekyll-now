---
layout: post
title: Robocomp for Arch Linux
published: true
---

Since some dependencies don't work out of the box for Robocomp's framework, I'm looking into how to make it an Arch Linux package. This is kind of a fun project for me, I have never made a package before.
[This](https://wiki.archlinux.org/index.php/creating_packages) is the Arch Linux documentation that I'm reading.

- The [ROS Index](http://rosindex.github.io/d/qt4-dev-tools/) has an awesome list of dependencies available by system. It's beautiful. 


## The dependencies are:


* pacman -> Easily installed by `sudo pacman -S git`



Name              | Repository | Name in Repository        |  Tested?
:---: | :---: | :---: | :---:
git | pacman | git | yes
git-annex | pacman | git-annex | yes
cmake | pacman | cmake | yes
g++ | pacman | gcc | yes
libgsl0-dev | pacman | gsl |yes
libopenscenegraph-dev | pacman | openscenegraph | yes
cmake-qt-gui | pacman | cmake | yes
zeroc-ice35  | pacman | zeroc-ice | no
freeglut3-dev  | pacman | freeglut | no
libboost-system-dev | pacman | boost-libs | no
libboost-thread-dev  | pacman | boost-libs | no
qt4-dev-tools | pacman | qt4 | yes
yakuake | pacman | yakuake | no 
python-pip | pacman | python-pip | yes  
python-pyparsing | pacman | python-pyparsing | no 
python-numpy | pacman | python-numpy | no 
python-pyside | pacman | python-pyside | no 
pyside-tools | pacman | python-pyside-tools | no
libxt-dev | pacman | lib32-libxtst OR libxtpy | **no** 
pyqt4-dev-tools | pacman | python-pyqt4 | **no** 
qt4-designer | pacman | qt4 | no 
libboost-test-dev | pacman | boost | no 
libboost-filesystem-dev | pacman | boost-libs | no 
libqt4-dev | yaourt | lib32-qt4 | no 
libqt4-opengl-dev | pacman | qt4 | yes 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ | ^^^^^^^^ | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ | ^^^

## Trying to run it from terminal


``` bash
Checking for module 'ccd'
--   No package 'ccd' found
-- Checking for module 'libccd'
--   No package 'libccd' found
```
We have to download ccd and libccd from the user repisitory. `yaourt -S libccd`
Tested --> This worked!

Now the new error is this:

```bash
CMake Error at /home/gaby/projects/robocomp/cmake/robocompLocal.cmake:106 (MESSAGE):
  Display.ice not found in any of the Slice directories
  (;;/home/gaby/projects/robocomp//interfaces/).
Call Stack (most recent call first):
  tools/rcinnerModelSimulator/src/CMakeLists.txt:52 (ROBOCOMP_WRAP_ICE)
```

It appears the ice package installed is not the correct one. Or something is wrong with installation folder.
Let's see. 

make printed this `/usr/bin/ld: cannot find -lIceUtil`

It's the ice dependency. 

- Let's try with ice-ssb from the user repository.--> It didn't work.
- Let's try with libice from pacman. --> It didn't work.

Commented line 36 in /home/gaby/robocomp/tools/rclogger/src/CMakeLists.txt. 

### [IceUtil was merged with Ice](https://doc.zeroc.com/display/Ice37/Upgrading+your+Application+from+Ice+3.6#UpgradingyourApplicationfromIce3.6-IceUtilLibraryRemoved) on version 3.7. I can't find where in the makefiles IceUtil is referenced to fix it.

But the dependency Robocomp works with is Ice 3.5. This is a little bad.

After a lot of searching I found the old version [here](https://github.com/zeroc-ice/ice.git).

### Project for Robocomp --> Actualizing Ice to version 3.7.
