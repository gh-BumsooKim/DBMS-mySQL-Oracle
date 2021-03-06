# How To Connect Website to DataBase (MySQL) Using Php or Python Based on APM on Windows 10

*Last updated: 01/02/2021*
  
*A Korean translation of this tutorial is located in the [translate folder.](https://github.com/gh-BumsooKim/APM-Connection-Website-to-DataBase-Tutorial-Windows-10/blob/master/translate/README.md)*


<b>\<Used Programming Language for ServerScript\></b>

A. php

B. python - CGI, mod_python, WSGI

C. perl

## Introduction
The purpose of this tutorial is to explain how to connect Website to MySQL DataBase based on APM Method. Word "APM" means 'A'pache(Web Server) + 'P'hp(Server Script Language) + 'M'ysql(DataBase). Also, instead of php server script language, you can use other language such as python and perl. Python used 3 method in this repo as CGI, mod_python and WSGI. At first, User fills data in Website made by html source. Then php receive data from html as form and submit tag method. Php received data store it to MySQL DataBase after connection DataBase for admin privileges. Open MySQl Workbench, you can check data in table for root account. (If you want to connect Apache Webser from external ip, you should remove php file in root following C:\xampp\htdocs\index.php and copy&paste your custom index.html and jump to STEP 4.)

## Steps
### 1. Install MySQL, XAMPP
In https://downloads.mysql.com/archives/installer/, you should download MySQL Project Version 8.0.11 and check Microsoft Windows Operating System. (You can download other Product Version in 8.0.XX. But I do not check upper than 8.0.XX version) (Please Check, Operating System is 64bit Windows10) Then can see msi file is downloaded. msi file is installer file using 'Windows Installer' and it means that "This Program will be intalled while checking important dll file to not fall into a 'dll hole problem'." And Set 'Type and Networking' like follwing referenced image. 

<p align="center"><img src="https://github.com/gh-BumsooKim/APM-Connection-Website-to-MySQL-DataBase-Tutorial-Windows-10/blob/master/docs/mysql.png" width="70%" height="70%"></img></p>

To install XAMPP, open url https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/7.2.9/. You should check XAMPP Version is 'xampp-win32-7.2.9-0-VC15-installer.exe'. (I do not check other XAMPP version is completely works.)

### 2. Run Apach Service
Open CMD with admin privileges, and Run the following commands in terminal.
```
CD %PROGRAMDATA%
CD MySQL
CD "MySQL Server 8.0"
NOTEPAD my.ini
```
Then, insert following commands in ini file line 403.
```
collation-server = utf8_unicode_ci
character-set-server = utf8
default_authentication_plugin = mysql_native_password
skip-character-set-client-handshake
```
(Change origin authentication into mysql_native_password method for php compatibility.)

Reboot OS.

Open XAMPP with admin privileges, and Check box 'Apache Service' and Press start button. (following image is reference.)

<p align="center"><img src="https://github.com/gh-BumsooKim/APM-Connection-Website-to-DataBase-Tutorial-Windows-10/blob/master/docs/xampp.png"></img></p>

Reboot OS.

### 3. Create User in MySQL Workbench
