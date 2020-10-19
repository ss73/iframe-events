# Iframe Events

This is a small technology demonstration that shows how IFrames can communicate with eachother. The idea is that the "top level" document which includes any number of Iframes acts as a message broker. Embedded Iframes can push events to their parent, and that parent will forward the event to any other Iframe on the page. 

## Setup
In order to demonstrate content from different origins being able to communicate cross-origin, a couple of DNS records has to be added to the `hosts` file.

Create two new entries in `/etc/hosts` (For Windows: `c:\windows\system32\drivers\etc\hosts`):
```
127.0.0.1   com.example.com
127.0.0.1   org.example.org
```
### Install http-server
A lightweight HTTP server is needed. Most UNIX-like operating systems have `http-server` in their package repositories, including Linux, Windows Subsystem for Linux (WSL) and MacOS with homebrew installed.
* Linux, WSL (ubuntu): `sudo apt-get install http-server`
* MacOS: `brew install http-server`

## Run the demo
open a new terminal
```
 $cd mainsite
 $http-server -p 8080
```
open a new terminal
```
 $cd subsite1
 $http-server -p 8081
```
open a new terminal
```
 $cd subsite2
 $http-server -p 8082
```
Open a browser and point it to [http://localhost:8080/](http://locahost:8080/)
