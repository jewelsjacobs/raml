# RAML OSPREY API DESIGNER

## Overview

This application provides a simple storage API plus a persistence plugin which enables you to run the [RAML API Designer](https://github.com/mulesoft/api-designer) locally (rather than use the APIHub cloud service) and still be able to manage and collaborate on your design.
Also using [osprey](https://github.com/mulesoft/osprey) to serve sample data defined in RAML definition.

## Requirements
The service is built with node.js, using express and mongodb.

### Installing Node.js
Go to [nodejs.org](http://nodejs.org), and click the Install button.

### Installing Node.js via package manager (Debian, Ubuntu, etc.)
View instructions [here](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager).

### Installing MongoDB
To install MongoDB on your specific platform, refer to the [MongoDB QuickStart](http://docs.mongodb.org/manual/installation/).

To start mongodb as background process:

`cd /usr/local/mongodb`  (mongodb installation directory)

`mongod --fork --logpath /var/log/mongodb.log`

### Installing Express and MongoDB Node.js Driver
From the top-level directory (e.g. raml-store):

`npm install `

## Running the Service
From the top-level directory (e.g. raml-store):

`node server.js`

If you prefer to run the server in the background [forever](http://blog.nodejitsu.com/keep-a-nodejs-server-up-with-forever) is awesome. 

`npm install forever`

`forever start server.js`

## Testing the Service

```
$ curl -i -X POST -H 'Content-Type: application/json' -d 
'{"name":"myfirstapi.raml","path":"/","contents":"#%25RAML%200.8%0Atitle:%20%20%20DONE!!!"}' 
http://localhost:3000/files
```

`$ curl -i -X GET http://localhost:3000/files`

## Coming soon
 - Generating faker mock data from RAML with [json-schema-processor](https://www.npmjs.org/package/json-schema-processor)
 - Decent docs
 - Decent CRUD services for mock data
 
[![Support via Gratipay](https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.png)](https://gratipay.com/jewelsjacobs/)
