# Provider Maps for the BitScoop API Toolbox

Welcome to our open source collection of Provider Maps for the BitScoop API Toolbox.

<img src="http://com-bitscoop-assets.s3.amazonaws.com/github/screenshots/apitoolboximg.png" alt=" " style="margin: auto; max-width: 100%;">

## [Provider Map Index](https://bitscooplabs.github.io)
https://bitscooplabs.github.io

## What is the API Toolbox?

The BitScoop API Toolbox makes APIs & microservices simple to integrate and easy to maintain. Our set of tools helps developers deal with data provider intricacies, inconsistencies, and annoyances that pervade app development. Using BitScoop you can more easily connect and interact with the data providers important to your work and projects.

Learn more with this demo:

https://github.com/bitscooplabs/api-toolbox-intro

## What is a Provider Map?

Provider Maps are the JSON configuration objects that you create to describe the interactions with data providers. They can include various sub-sections such as a description of the authentication scheme the data provider uses and endpoints from which you can obtain data.

Many data providers require permission from your end users to read their data. This process is generally handled by a workflow such as OAuth or OpenID and can be handled by the BitScoop API Toolbox with some configuration on the Provider Map. You'll need to instantiate Connections to the data provider behind your Provider Map as a place to store authentication and characterizing information about an end user who has giving you permission to read their data. In most cases you'll have one Connection per end user and BitScoop will automatically store the relevant information used to identify this user in the data provider's system.

<img src="http://com-bitscoop-assets.s3.amazonaws.com/github/screenshots/bitscoopdiagram.png" alt=" " style="margin: auto; width: 100% max-height: 200px">

## How to use Provider Maps:

Any Provider map can be copied out of this repository and used to create a new Provider Map in the API Toolbox, either by using the Developer Portal or by submitting it directly to the BitScoop API.

### Create a Provider Map via the Developer Portal


###### 1. Create an API Key

<img src="http://com-bitscoop-assets.s3.amazonaws.com/github/screenshots/1createapikey.png" alt=" " style="margin: auto; max-width: 100%;">

###### 2. Create a Provider Map

<img src="http://com-bitscoop-assets.s3.amazonaws.com/github/screenshots/2createprovidermap.png" alt=" " style="margin: auto; max-width: 100%;">

###### 3. Add the Provider Map JSON to the Editor

<img src="http://com-bitscoop-assets.s3.amazonaws.com/github/screenshots/3addprovidermap.png" alt=" " style="margin: auto; max-width: 100%;">

### Create a Provider Map via an API Request


###### 1. Create an API Key

<img src="http://com-bitscoop-assets.s3.amazonaws.com/github/screenshots/4createkey.png" alt=" " style="margin: auto; max-width: 100%;">

###### 2. Post to the Provider Endpoint of the BitScoop API

````
curl --request POST \
  --url https://api.bitscoop.com/providers/ \
  --header 'authorization: Bearer {{insert_bitscoop_api_key}}' \
  --header 'content-type: application/json' \
  --data '{\n
      "version": "1.0",\n
        "name": "Sample JSON Placeholder API",\n
  "url": "https://jsonplaceholder.typicode.com",\n
  \n
  "headers": {\n
    "X-Global": "Header Global"\n
  },\n
  \n
  "parameters": {\n
    "globalParam": "foo"\n
  },\n
  \n
  "endpoints": {\n
    "users": {\n
      "route": "/users",\n
      "single": {\n
        "route": "/users/{{ identifier }}"\n
      },\n
      "model": {\n
        "key": "id",\n
        "fields": {\n
          "id": "integer",\n
          "name": "string",\n
          "username": "string",\n
          "email": "email"\n
        }\n
      },  \n
    "headers": {\n
      "X-Endpoint": "Header Endpoint"\n
    },\n
    "parameters": {\n
      "endpointParam": "foo"\n
    }\n
    }\n
  }\n
}'`
````

Learn more at:

https://developer.bitscoop.com/learn/providers

#### Create a Connection

Optionally, you can create connections to APIs with multi legged authorization.


````
curl --request POST \
  --header "authorization: Bearer {{insert_bitscoop_api_key}}" \
  --url "https://api.bitscoop.com/providers/{{insert_bitscoop_api_key}}/connections"
````

https://developer.bitscoop.com/learn/connections

## See someting missing? Got a better idea? Contribute!

#### Missing an endpoint? Provider map not doing what you wish?

#### Contribute and help us map every API!

Please see our [Contributing Document](https://github.com/bitscooplabs/provider-maps/CONTRIBUTING.md)

## Is your API Private?

#### Easily create your own provider map. Learn more:

https://developer.bitscoop.com/learn/providers

## Troubleshooting / Issues:

If you have any issues using BitScoop API Toolbox, please use our [Support page](https://bitscoop.com/support).

Please note that theses are not guaranteed to be correct. If you find any issues with a, feel free to make corrections in the map(s) you create from that, email BitScoop about the problem you are encountering, or create a ticket on our GitHub repository.

To document issues with the open Source Provider Maps:

* You need a [GitHub account](https://github.com/signup/free)
* Submit an [issue ticket](https://github.com/python-social-auth/social-core/issues)
  for your issue if there is no one yet.
	* Describe the issue and include steps to reproduce if it's a bug.
	* Make sure to mention the earliest version that you know is affected.
* If you are able and want to fix this, fork the repository on GitHub.
