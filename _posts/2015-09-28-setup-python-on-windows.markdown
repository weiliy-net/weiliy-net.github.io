---
author: wiadmin
comments: true
date: 2015-09-28 11:13:04+00:00
layout: post
slug: setup-python-on-windows
title: Setup Python on Windows
categories:
- Python
---

## Install Python

1. Downlaod python2 32bit from [Python Official Site](https://www.python.org/downloads/windows/)


2. [Using Windows Installer](https://www.python.org/download/releases/2.4/msi/) to install the python, just run: `msiexec /i python-*.msi TARGETDIR=c:\python2\32bit`


3. [Configure Path](https://technet.microsoft.com/en-us/library/ff730964.aspx?f=255&MSPPError=-2147217396)
    
    $user_path = [Environment]::GetEnvironmentVariable("Path", "User")
    $user_path += ';c:\python2\32bit;C:\python2\32bit\Scripts'
    [Environment]::SetEnvironmentVariable("Path", $user_path, "User")

## Update PIP

[Upgrade pip on windows](https://pip.pypa.io/en/stable/installing/#install-pip)
    
    python -m pip install -U pip
