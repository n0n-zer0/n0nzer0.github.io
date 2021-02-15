---
description: grabbing the low hanging fruit
---

# Whitebox - phase 2

## Plan

It is now time to identify which of the vulnerable/valuable functions is adequately protected and which ones are not. You try to go through this for each of the identified vulnerable/valuable features, don't get stuck to long on any single feature

* Identify the parts of code that is responsible for handling your data in this feature
* Analyse how authorization is done for this function
* Use BURP or a simple POC to send manipulated data to the target function
* Follow your user input, throughout the layers of the application
  * Identify any transformations/validations done on the input data
* Analyse and understand the code flow of the vulnerable/valuable function
  * use step by step debugging when necessary
  * look at the logs
* determine whether a feature is vulnerable or not
  * i.e. try to get a confirmation that the basis of your exploit works \(SQL sleep, simple XXE is parsed etc...\)

