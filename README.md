# Azure Application Gateway with path based routing and Apache Server

## Application Gateway (SSL terminator) path based routing

## Path based route

- Under the root Apache directory (usually ```/var/www/html```) create a folder (```/var/www/html/app```). You should end up with the following URIs:
  - Root site: http://host
  - App Site: http://host/app

In App Gateway set a path ```/app/*``` pointing to the Apache server on the pool.

> **Note:** Under this configuration all requests arriving at the Application Gateway with the path /app/* will be routed to the Apache server assigned to the backend pool at the app site (http://host/app)

## Default route

- Configure the Application Gateway with the default backend pool pointing to the Apache server.
- Do not configure a path based route

> **Note:** Under this configuration all requests arriving at the Application Gateway that do not have a matching path will be routed to the root site (http://host) of the Apache server defined in the backed pool.
