---
layout: post
title: "Laravel is a great framework"
date: 2014-02-18 09:28
comments: true
categories: [PHP, Laravel, SOAP]
---

I recently had to work on a project that required hooking into Magento's SOAP API and parsing orders from an Excel spreadsheet into
the Magento dashboard. Although Magento has a REST API, it doesn't seem to be nearly as capable as the SOAP API, and offers no real
functionality other than the ability to get orders, products, and so on. Having never really worked with a SOAP API, I went to my usual
framework (Ruby on Rails) and looked for a SOAP gem. I found [Savon](http://savonrb.com/) and thought I would give that a shot. While
Savon works for most applications, something about the way Magento was requiring the request body to be formatted wasn't jiving with 
how Savon wanted to format it for me. 

### Laravel to the Rescue
----
I decided that I would have to use PHP for this, since PHP has support for SOAP built right in, and also because all of the examples 
Magento gave on their site were for PHP. Creating a soap client in PHP is as simple as:
``` php
$client = new SoapClient('your-wsdl-here');
```
