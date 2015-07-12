## clinical:extended-api

API extensions for Meteor core objects.


### Installation

First, install the extended-api package from the command line, like so:

````js
meteor add clinical:extended-api
````

### API

The Session object will support the following API with this package installed:  

````js
Session.set()
Session.setDefault()
Session.setAll()
Session.get()
Session.equals()
Session.toggle()
Session.clear()
````

````js
Mongo.Collection.drop()
````


### Testing  

View the TinyTests results by doing the following:  
````js
cd myapp/packages/extended-api
meteor test-packages
````


### Examples  

#### Session.toggle(key)  
Function, Client
Toggle a variable true/false in the session.

````js
//example
Session.setDefault("widgetIsOpen", false);

Template.myTemplate.events({
  'click #displayWidgetButton':function(){
    Session.toggle("widgetIsOpen");
  }
});
````

#### Session.clear(key)  
Function, Client  
Toggle a variable true/false in the session.

````js
//example
Session.setDefault("selectedPurchaseItemId", Meteor.user().profile.selectedItemId);

Template.myTemplate.events({
  'click #emptyShoppingCart':function(){
    Session.clear("selectedPurchaseItemId");
  }
});
````

#### Mongo.Collection.drop()  
Function, Server
Drop the entire collection.  
````js
var Foo = new Mongo.Collection(null);
Foo.insert({text: "foo"});
Foo.drop();
````

### Licensing

MIT License.  Use as you will.
