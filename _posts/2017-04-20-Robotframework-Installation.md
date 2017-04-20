---
layout: post
title: Robotframework installation on ubuntu
category: robotframework
tags: [automation, robotframework]
---

## Robot Framework Installation on Ubuntu

Generally robot framework can be installed on any platforms. This blog will be description how to install Robot on Linux Ubuntu.

### Steps of installation

**Step 1:** Install Python

It has been installed on Linux as default (see Robotframework on Ubuntu 16.04)

**Step 2:** Verify Python version

`$ python --version`

Command result will be

`$ Python 2.7.6`

**Step 3:** Install robotframework

`$ sudo pip install robotframework`

**Step 4: **Verify robotframework installation

`$ robot --version`

Command result will be

`$ Robot Framework 3.0 (Python 2.7.6 on linux)`

**Step 5:** Install Selenium2Library

`$ sudo pip install robotframework-selenium2library`

**Step 6:** Install Selenium

Since Selenium2Library has some dependencies for selenium library, you need to install selenium library. The easy way of installing selenium library is to use pip. You can use the following command to install selenium.

`$ sudo pip install -U selenium`

**Step 7:** Install wxpython

RIDE is a light-weight and intuitive editor for Robot Framework test case files. Since RIDE uses wxpython 2.8, you need to install the package as well. RIDE does not yet support Python 3.

To install wxpython 2.8 or later version, visit the [wxpython download page](http://wxpython.org/download.php#msw)  and download the version depending on your OS. Please note that the package has 32 bit and 64 bit, so you need to install the corresponding package depending on your operating system version. 

**Step 8:** Install robotframework IDE (RIDE)

`$ sudo pip install robotframework-ride`

**Step 9:** Verify RIDE installation

`$ ride.py`

The RIDE window will pop up.

### Robotframework on Ubuntu 16.04

Since Ubuntu 16.04 repository has python-wxgtk3.0 installation as default which does not support Robotframework. The solution is using python-wxgtk2.8 instead of python-wxgtk3.0

**Step 1:** Add the repoisitory and update package list

`$ echo "deb http://archive.ubuntu.com/ubuntu wily main universe" | sudo tee /etc/apt/sources.list.d/wily-copies.list`
`$ sudo apt update`

**Step 2:** Install  python-wxgtk2.8

`$ sudo apt install python-wxgtk2.8`

**Step 3:** Remove repository entry and update package list again 

`$ sudo rm /etc/apt/sources.list.d/wily-copies.list`
`$ sudo apt update`
