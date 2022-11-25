[![Build master](https://github.com/benkoben/azsubnetcalc/actions/workflows/unit-test.yaml/badge.svg)](https://github.com/benkoben/azsubnetcalc/actions/workflows/unit-test.yaml)

Subnetcalc
===

A simple module that calculates the next possible subnets inside a pre-existing subnet. This can be usefull when you dynamically want to create subnets within a pre-existing virtual network. 

Features
===
* Supports multiple address spaces within a single VNET object
* No authentication necessary. The program relies on passing in JSON formatted data.
* Logic can be imported as a module by different programs, I wrote an example in here https://github.com/benkoben/subnetfinder

Limitations
===
* **Calculates best effort** - whenever a required subnet size is not the module will exclude it from the output. Meaning that error handling needs to be done by the consumer. An example scenario is when three 24 subnets are requested but the existing virtual network only fits two of them. Then the output from this module will only have a lenght of two.

Why I created this
===

I created this tool in order to calculate subnets prefixes within an existing virtual network without human interaction. For instance whenever a resource package is ordered from within an ITSM systems, it could trigger an automation which uses this module to calculate the required subnets and deploy the resources accordingly.

