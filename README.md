# webinos TV API #

**Service Type**: http://webinos.org/api/tv

The main concept of TV API is to provide the interface between webinos and your setop box or TV.


## Installation ##

To install the TV API you will need to npm the node module inside the webinos pzp.

For end users, you can simply open a command prompt in the root of your webinos-pzp and do: 

	npm install https://github.com/webinos/webinos-api-tv.git

For developers that want to tweak the API, you should fork this repository and clone your fork inside the node_module of your pzp.

	cd node_modules
	git clone https://github.com/<your GitHub account>/webinos-api-tv.git
	cd webinos-api-tv
	npm install


## Getting a reference to the service ##

To discover the service you will have to search for the "http://webinos.org/api/tv" type. Example:

	var serviceType = "http://webinos.org/api/tv";
	webinos.discovery.findServices( new ServiceType(serviceType), 
		{ 
			onFound: serviceFoundFn, 
			onError: handleErrorFn
		}
	);
	function serviceFoundFn(service){
		// Do something with the service
	};
	function handleErrorFn(error){
		// Notify user
		console.log(error.message);
	}

Alternatively you can use the webinos dashboard to allow the user choose the TV API to use. Example:
 	
	webinos.dashboard.open({
         module:'explorer',
	     data:{
         	service:[
            	'http://webinos.org/api/tv'
         	],
            select:"services"
         }
     }).onAction(function successFn(data){
		  if (data.result.length > 0){
			// User selected some services
		  }
	 });

## Methods ##

Once you have a reference to an instance of a service you can use the following methods:



## Links ##

- [Specifications](http://dev.webinos.org/specifications/api/tv.html)
- [Examples](https://github.com/webinos/webinos-api-tv/wiki/Examples)

