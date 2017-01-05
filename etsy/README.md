# Etsy

| Provider Map | File Name | |
|------------------------------|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Etsy v2 API | etsy_v2.json | [![Etsy](https://d233zlhvpze22y.cloudfront.net/github/bitscoopaddbuttonxsmall.png)](https://bitscoop.com/maps/create?source=https://raw.githubusercontent.com/bitscooplabs/provider-maps/master/etsy/etsy_v2.json) |

Etsy is an online marketplace for buying and selling handmade things. The Etsy API lets you develop applications built on this fast growing e-commerce platform.

## Special Note about Etsy OAuth1

Etsy uses a proprietary implementation of OAuth1 to add scope to the API keys they generate. At this time, BitScoop does not plan on modifying its OAuth1 implementation to cover this non-standard implementation. The current solution for authenticating with the Etsy API is to determine the scopes that you'll need based on the endpoints you plan to use and to manually set those scopes in the request_token URL in the auth block. Per Etsy's documentation, the scopes should be space-separated and URL encoded. For full details, see their documentation.

## Documentation
https://www.etsy.com/developers/documentation

## Reference

#### Programmable Web
https://www.programmableweb.com/api/etsy

#### Wikipedia
https://en.wikipedia.org/wiki/etsy
