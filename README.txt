===================
api-wrappers-python
===================

Source available: https://github.com/miiCard/api-wrappers-python
Licensed under BSD 3-Clause licence (see LICENSE.txt)

Python wrapper classes around the miiCard API.

This repository houses the source for the latest version of the miiCard 
Consumers library available on PyPI. 

See http://www.miicard.com/developers for more information.


What is miiCard
===============

miiCard lets anybody prove their identity to the same level of traceability as 
using a passport, driver's licence or photo ID. We then allow external web 
applications to ask miiCard users to share a portion of their identity 
information with the application through a web-accessible API.


What is the library for?
========================

miiCard's API is an OAuth-protected web service supporting SOAP, POX and JSON -
documentation is available. The library wraps the JSON endpoint of the API, 
making it easier to make the required OAuth signed requests.

You can obtain a consumer key and secret from miiCard by contacting us on our 
support form, including the details listed on the developer site.

Pull the library into your own application by downloading the latest released 
version from PyPI.


Usage
=====

You'll need to implement your own OAuth exchange with miiCard.com's OAuth 
endpoint to obtain an access token and secret for a user. Once you've got your 
consumer key and secret, access token and access token secret you can 
instantiate an API wrapper:

	api = MiiCardOAuthClaimsService("consumer_key", "consumer_secret", 
									"access_token", "access_token_secret")

Then make calls against it simply:

	user_profile_response = api.get_claims().data

	user_first_name = user_profile_response.data.first_name


Dependencies
============

The library takes a dependency on simplegeo-oauth2, but uses a patched version 
of it to correct a few issues.


Contributing
============

* Use GitHub issue tracking to report bugs in the library
* If you're going to submit a patch, please base it off the development branch 
  - the master reflects the latest version published to PyPI but may not 
  necessarily be bleeding-edge
* Join the miiCard.com developer forums to keep up to date with the latest 
  releases and planned changes
