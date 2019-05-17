# Azure Application Gateway with path based routing and Apache Server

## Application Gateway (SSL terminator) path based routing

## Path based route

Under the root Directory (```/var/www/html```) create a folder (```/var/www/html/app```). You should end up with the following URIs:

Root site: http://host
App Site: http://host/app

In App Gateway set a path ```/app/*``` pointing to the Apache server on the pool.

> Under this configuration all requests arriving at the Application with the path /app/* will be router to the Apache server assigned to the pool at the app site (http://host/app)

## Default route

Configure the AppGw wit the default backend pool pointing to the Apache server.
Do not configure a path

> Under this configuration all requests arriving at the AppGw with that do not have a match in the paths will be routed to the root site (http://host) of the Apache server defied in the backed pool.
