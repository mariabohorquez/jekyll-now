---
layout: post
title: Robocomp for Arch Linux
published: true
---

Since some dependencies don't work out of the box for Robocomp's framework, I'm looking into how to make it an Arch Linux package. This is kind of a fun project for me, I have never made a package before.
[This](https://wiki.archlinux.org/index.php/creating_packages) is the Arch Linux documentation that I'm reading.

- The [ROS Index](http://rosindex.github.io/d/qt4-dev-tools/) has an awesome list of dependencies available by system. It's beautiful. 

## The dependencies are:

* pacman --> Easily installed by `sudo pacman -S git`

Name | Repository | Name in Repository | Tested?
:---: | :---: | :---: | :---:
git | pacman | git | yes
git-annex | pacman | git-annex | no
cmake | pacman | cmake | yes
g++ | pacman | gcc | yes
libgsl0-dev | pacman | gsl |yes
libopenscenegraph-dev | pacman | openscenegraph | yes
cmake-qt-gui | pacman | cmake | yes
zeroc-ice35  | pacman | zeroc-ice | no
freeglut3-dev  | pacman | freeglut | no
libboost-system-dev | pacman | boost-libs | no
libboost-thread-dev | pacman | boost-libs | no
qt4-dev-tools | pacman | qt4 | yes
yakuake | pacman | yakuake | no 
python-pip | pacman | python-pip | yes  
python-pyparsing | pacman | python-pyparsing | no 
python-numpy | pacman | python-numpy | no 
python-pyside | pacman | python-pyside | no 
pyside-tools | pacman | pyside-tools | no
libxt-dev | pacman | lib32-libxtst | **no** 
pyqt4-dev-tools | pacman | python-pyqt4 | **no** 
qt4-designer | pacman | qt4 | no 
libboost-test-dev | pacman | boost | no 
libboost-filesystem-dev | pacman | boost-libs | no 
libqt4-dev | yaourt | lib32-qt4 | no 
libqt4-opengl-dev | pacman | qt4 | yes 
