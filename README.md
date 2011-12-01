#Oodebe

Oodebe is an asynchronous I/O based framework built on node.js for providing a consistent client (REST) API 
for synchronizing operations on one or more back-end server modules.


* Provides facilities to develop, test and deploy a REST API server
* Each API call can be constructed as a script
* Scripts can be executed as either native node.js scripts or one of the supported plugins
* Plugins allow scripts to access various REST servers such as Neo4j, SOLR, MongoDB, and Lily using their REST interface
* Additional plugins can be written in the form of simple JSON configuration files

##How to Install

* Download the zip from git repo and extract it
* Make sure you have installed the required back-end servers such as HBase, Solr, Lily, MongoDB etc.
* Edit configuration variables in conf.js so as to map the various server access details (see configuration variables below)
* Start oodebe server:   
   
   node index.js

* Start oodebe web console (assuming server is configured on port 8000:
       

   http://localhost:8000
   
## Requirements

* [Node 0.4.12] (http://nodejs.org/)
* [Async Module of Node] (https://github.com/caolan/async)
* [Rest Module of Node] (https://github.com/danwrong/restler)
* [Mongo Module of Node] (https://github.com/guileen/node-mongoskin)
* [Solr Module of Node] (https://github.com/gsf/node-solr)
* [Log Module of Node] (https://github.com/visionmedia/log.js)
* [UUID Module of Node] (https://github.com/broofa/node-uuid)
* [Cluster Module of Node] (https://github.com/LearnBoost/cluster)
* [Connect Module of Node] (https://github.com/senchalabs/connect)

## Configuration Variables

* Neo4j REST URL e.g. 'neo4jurl':"http://localhost:7474/db/data/ext/GremlinPlugin/graphdb/execute_script",
* Lily REST URL e.g. 'lilyurl':"http://localhost:12060/repository/record/",
* Solr REST URL e.g. 'solrurl':"http://localhost:8983/solr/select?",
* Mongodb Connection Url e.g. 'mongodbhost':"localhost:27017/test?auto_reconnect",
* Server port on which server run e.g. 'serverport':'8000',
* Host of solr  e.g.	'solrhost':'localhost',
* Port of Solr e.g. 'solrport':'8983'
* We can define our own config variable and use them in program. e.g. "newconfig": "value" can be use in program by
  config.newconfig it will give "value".

## Functions 
### processquery
   Input : query , request ,responsehttp
   query : input parameter by GET or POST
   request : http.server request parameter of callback
   responsehttp: http.server response parameter of callback
   
### login
   
   Input : query , request ,responsehttp
   query : input parameter by GET or POST
   request : http.server request parameter of callback
   responsehttp: http.server response parameter of callback
   
### logout 
 
   Input : query , request ,responsehttp
   query : input parameter by GET or POST
   request : http.server request parameter of callback
   responsehttp: http.server response parameter of callback

### writeLog
   Input : file, string, flag, mode, skipDate
   file : Name of the file
   string : content of file
   flag : e.g. 'a' for apped mode
   mode : e.g. 755
   skipDate : Date which is to skip
### delFromSolr

   Input : id, query, callback
   id : document id to be deleted 
   query : input parametere
   callback : function to call
### addToSolr 
   Input : doc,commit,callback
   doc :  new document to add
   commit : true /false
### loadScript
   load a file and return it's contents as an object
   Input : request, callback
   request :input parameter by GET or POST 
### execScript
  Input : request, callback
  request :input parameter by GET or POST 
### parseInputParamters  
 parse the input parameter (string) by \n and first occurence of =
 Output : json
 Input : dataparaminput (input parameter request.paraminput)
 
### saveScript
  Input : request, callback
  request :input parameter by GET or POST 
  
### savefile   
  Input : request, callback
  request :input parameter by GET or POST 

### jsoncurl

   Input : burl, bdata, callback
   burl : url of the curl
   bdata : data to send with curl request
   
### deleteScript

  Input : query, callback
  query : input parameter by GET or POST 
   
### getScripts
   Input : file,results,callback
   file : directory name in which all files are to be traversed.
   results : array in which result of the files will be stored.
   
### fileprocess
   Input : request, responsehttp
   Output :  return the file with http respnse .
   
### sortScripts
   Input : query, callback 
   query : input parameter by GET or POST 
### newuser
   Input : user, callback
   user : data of user in json which we want to store.
   
### authuser
    Input : request, user, callback
    request : http request 
    user : input parameter by GET or POST  
   
   

   
   
   
   
   
   
   
   

## Running Sample Scripts

After installation, if you start the oodebe web console, you will see various sample scripts for Lily, Neo4j, Node.js 
and Solr.  These scripts assume that you have all these servers correctly installed and configured in conf.js

