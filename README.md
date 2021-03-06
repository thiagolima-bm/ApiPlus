# API Plus for Magento

[![Build Status](https://travis-ci.org/tiagosampaio/TS_ApiPlus.svg?branch=master)](https://travis-ci.org/tiagosampaio/TS_ApiPlus)

Rather than using (slow) SOAP to call to Magento's API why not to simply send a *POST* to an endpoint provinding your authentication data in request headers and a JSON-encoded body with the resource name you want to consume with arguments needed for the call?

API Plus for Magento is a module that improves how Magendo API can be consumed by thirty part applications. By using API Plus in your Magento store you make the API connection much eaiser but with the same abstraction and providing the same flexibility and security that Magento platform already provides for all its community.

## NOTE

This documentation is not complete but I'm working on it to improve and make it better everytime I have a little free time.

## Features

- **Much easier!**: API Plus is much, much, much easier to be used in your Magento platform. By using it you don't need to make SOAP calls anymore.
- **Flexibility**: API Plus uses the Magento API's abstraction so, the same flexibility is provided by API Plus.
- **Security**: API Plus is as secure as Magento's authentication system.
- **Performance**: By using API Plus your API connections and results will be much faster then using the default SOAP calls.

## Authors, contributors and maintainers

Author:
- [Tiago Sampaio](http://tiagosampaio.com)

## Compability

- PHP: 
  - 5.3
  - 5.4
  - 5.5
- Magento CE: 
  - 1.6.2.0
  - 1.7.0.2
  - 1.8.0.0
  - 1.8.1.0
  - 1.9.0.1
  - 1.9.1.0
- Magento EE: 
  - 1.11.0.0
  - 1.11.0.2
  - 1.11.1.0
  - 1.11.2.0
  - 1.12.0.0
  - 1.12.0.1
  - 1.12.0.2
  - 1.13.0.2
  - 1.13.1.0
  - 1.14.0.1
  - 1.14.1.0

## Documentation

### Basic

It's quite simple! Rather then using SOAP process described in [Magento Webservice Documentation](http://devdocs.magento.com/guides/m1x/api/soap/introduction.html) all you need to do is to send a POST request to:

[https://www.yourmagentohost.com/`api/json`](#)

Providing the following authentication parameters in request header:

Parameter Key | Parameter Value
--- | ---
`apiUsername` | [Your Magento's API Username]
`apiKey` | [Your Magento's API Secret Key]

And the body in JSON format:

```json
{
  "resource": "catalog_product.list"
}
```

If you need to send any arguments, like you do in SOAP request for some resources you simply add a new node `args` in the body:

```json
{
  "resource": "catalog_product.list",
  "args": {
    "complex_filter": [
      {
        "key": "type",
        "value": {
          "key": "in",
          "value": "configurable,grouped"
        }
      }
    ]
  }
}
```


## License

[MIT License](LICENSE.txt)

## Links

Will be added soon :)
