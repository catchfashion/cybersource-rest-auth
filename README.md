# AuthenticationSDK
This project provides a simple Node.js helper library that simplifies authentication to the CyberSource REST API

## Requirements
* Node.js version 8.11.1
* npm version 5.8.0
* A cybersource-rest-auth-nodejs account (see _Registration & Configuration_ section below)

_Note: Support for building the SDK with npm has been made.
 All initial libraries were installed with npm, however._
 
 ## Dependencies
* app-root-path^2.1.0 		:  access your application's root path
* chai^4.1.2				      :  assertion library
* chai-as-promised^7.1.1	:  asserting facts about promises
* collections^5.1.2			  :  implementations of common data structures
* jwt-simple^0.5.1			  :  JWT encode and decode module
* memory-cache^0.2.0		  :  simple in-memory cache
* node-forge^0.7.5			  :  native implementation of TLS and other cryptographic tools
* promise^8.0.1				    :  simple implementation of Promises
* winston^2.4.2				    :  logging framework  
* request^2.85.0			    :  for http connection
* mocha^5.2.0 				    :  unit testing framework
* mocha-sonarqube-reporter^1.0.1	: to generate coverage report
* nyc^12.0.2				      :  to integrate test coverage with sonarQube
* sonar-scanner^3.1.0 		:  to scan coverage for sonar


## To run Authentication SDK

The Authentication SDK works for POST, GET, PUT and DELETE requests.
It works with any one of the two authentication mechanisms, which are HTTP signature and JWT token.

#### To set your API credentials for an API request, Configure the following information in cybs.json file:
  
  * Http

```
   "authenticationType"  : "http_signature"
   "merchantID"	         : <merchantID>
   "runEnvironment"      : "CyberSource.Environment.SANDBOX"
   "merchantKeyId"       : <merchantKeyId>
   "merchantsecretKey"   : <merchantsecretKey>
   "enableLog"           : true
   "logDirectory"        : "./log"
   "logMaximumSize"      : 10485760
   "logFilename"         : "cybs"
```
  * Jwt

```
   "authenticationType"  : "jwt"
   "merchantID"	         : <merchantID>
   "runEnvironment"      : "CyberSource.Environment.SANDBOX"
   "keyAlias"            : <keyAlias>
   "keyPass"             : <keyPass>
   "keyFileName"         : <keyFileName>
   "keysDirectory"       : <keysDirectory>
   "enableLog"           : true
   "logDirectory"        : "./log"
   "logMaximumSize"      : 10485760
   "logFilename"         : "cybs"
```

### Switching between the sandbox environment and the production environment
Cybersource-rest-auth maintains a complete sandbox environment for testing and development purposes. This sandbox environment is an exact 
duplicate of our production environment with the transaction authorization and settlement process simulated. By default, this SDK is 
configured to communicate with the sandbox environment. To switch to the production environment, set the appropriate environment 
constant in cybs.json file.  For example:

```nodeJS
// For PRODUCTION use
  "runEnvironment"      : "CyberSource.Environment.PRODUCTION"
```

### Configure the following information in cybs.json file
*	Authentication Type:  Merchant should enter “HTTP_Signature” for HTTP authentication mechanism or “JWT” for JWT authentication mechanism.
*	Merchant ID: Merchant will provide the merchant ID, which has taken from EBC portal.
*	MerchantSecretKey: Merchant will provide the secret Key value, which has taken from EBC portal.
*	MerchantKeyId:  Merchant will provide the Key ID value, which has taken from EBC portal.
*	keyAlias: Alias of the Merchant ID, to be used while generating the JWT token.
*	keyPassword: Alias of the Merchant password, to be used while generating the JWT token.
*	keyfilepath: Path of the folder where the .P12 file is placed. This file has generated from the EBC portal.
*	Enable Log: To start the log entry provide true else enter false.
*	LogDirectory: If log is enabled and valid log directory is provided, log files will get created here. Otherwise log files will be created in default location inside project base directory.


## SDK Usage Examples and Sample Code
 * To get started using this SDK, it's highly recommended to download our sample code repository.
 * In that respository, we have comprehensive sample code for all common uses of our API.
 * Additionally, you can find details and examples of how our API is structured in our API Reference Guide.

The API Reference Guide provides examples of what information is needed for a particular request and how that information would be
formatted. Using those examples, you can easily determine what methods would be necessary to include that information in a request
using this SDK.


## Running the Samples From the Command Line
* Clone this repository:
```
    $ git clone https://github.com/CyberSource/cybersource-rest-auth-nodejs
```
* Install the dependencies project by project (Go to each base folders, where package.json is present. Run the command)
```
    $ npm install
```
* Run the individual samples from CyberSource-Authentication-SDK-nodeJS directory by name.
```
    $ node src\[CodeSampleName]
```
For example: 
```
    $ node src\GetMethod.js
```
  
## License
This repository is distributed under a proprietary license.
