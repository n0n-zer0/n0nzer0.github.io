---
description: going by technology/vulnerability type
---

# Whitebox - phase 3

## Plan

We have exhausted our "natural leads"or the code base is so big and the application so unfamiliar \(maybe API only without UI\) that going through individual features is not a viable approach. This is also where \(if you did not in phase 1\) you would use static code analysers and other tools to quickly indentify any problem areas.

The findings you get from these results differ in that you will have to analyze them "bottom-up". Before we went into the functions from the endpoints/users side and follewed the users input into the potential vulnerable function. NOW we find potential vulnerable functions and we have to determine if they can be triggered and influenced by outside actors.

* Use Static code analysers to find potentiall weaknesses
* Use GREP/ REGEX to look for:
  * SQL queries
    * string concatination
  * XXE
  * Any File, URL handling
  * Command injection \(command, sys, etc\)
  * Eval 
  * bad comparison operators \(php type juggling\)
  * Deserialization
  * etc....
* try and go through the results, taking 1/5min \(or longer depending on the number of results or the code base\) to determine if something should be investigated furher or not
* prioritise your list of findings
* go through the top5 and spend 10 min on each to determine if:
  * it can be triggered by outside actors \(users\)
  * Userinput can reach the code



