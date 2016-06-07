vaadin-pouchdb
========

A polymer web component wrapping [PouchDB](http://pouchdb.com/).

It's goal is the 

## Example

use the local database `chat` which will be synchronised with the one specified in the `remote` parameter. Remote could be either couchdb or pouchdb. If you don't specify any remote, it will be use a local instance only.

By default, any changes in the `data` array will be propagated to the database, and any change in the database to the array, so as you can use polymer databinding as usual.

Also by default, it queries all items in the database, but you could configure the `queryString` parameter, or just set an index to use it.

The index parameter uses the provided attribute to query the database and sort the data, also it adds the index to the database if it does not exist yet, the user has to be allown to create the index though.

```
    <vaadin-pouchdb id="db"
      dbname="chat"
      index="ts"
      data="{{items}}"
      remote="http://user:password@localhost:5984/chat"
     ></vaadin-pouchdb>
```

## For GWT users

Once you have added the gwt-polymer-api

You can wrap the element using vaadin the gwt-api-generator:

```
  $ sudo npm install vaadin/gwt-api-generator -g
  $ bower install manolo/vaadin-pouchdb
  $ gwt-api-generator 
```

Then you will get all needed classes in your `src/main/java` folder

Your project should also depend on vaadin gwt-polymer-elements

