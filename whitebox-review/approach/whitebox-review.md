---
description: getting a overview
---

# Whitebox - phase 1

## plan

* Identify language/architecture/libraries
  * is a framework being used ?
  * look at package.json, pom.xml files etc
* Familiarize yourself with the application structure
  * Identify the entry points for the webpages or API
    * here the input data is usually transformed to the applications internal models
    * is there any mapping/transformations/validations being done on the input data ? 
  * Identify the "service or business logic" layer of the application
    * here the application acts on the input data
  * Identify the Data layer, 
    * here the applications data is either: stored, retrieved or manipulated
  * Identify any utility or helper functions or libraries
* Analyse the Authentication/session mechanism/endpoints
  * Where does the user login ?
  * how is the password comparison done ?
  * how does the reset functionality work ?
    * how is the reset token 
      * generated ?
      * stored ?
      * shared ?
      * logged ?
  * how are the user rights stored/modelled ?
  * how is the session persisted ? \(cookie, token\)
    * how is this generated ?
    * where is it stored
  * how is the application "aware" of the current session
* Analyse the Authorization mechanisms
  * how are functions protected \(i.e. when and how is a users roles and permissions checked\) ?
  * Is there a central implementation responsible for these checks ?
    * yes -&gt; review the implementation thoroughly!
      * is it used **EVERYWHERE are there any exceptions to the rule** ? later in the review when you look at code you want to attack, validate this again.. 
    * no -&gt; review the mechanism ad-hoc for functions that seem of interest
* Analyse the Data layer
  * What Database is being used ?
  * Object-relational mapping \(ORM\) technology \(entity framework, hibnernate etc\)
  * how are queries constructed ?
  * any unsafe handling of user data ? \(i.e. sql injection\) ?
* Analyse the utility functions 
  * Any Whitelisting/blacklisting
  * Any custom sanitization ?
  * Any central "randomizer" implementation
  * Any File handling \(filetype checks, image handling\)
* Run static code analysers
  * this gives you a rough idea of potentiall problems
  * spend 10/20 minutes analysing some of the results, mark and prioritise the most promising ones



