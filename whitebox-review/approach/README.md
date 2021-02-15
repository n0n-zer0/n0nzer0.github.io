# Approach

## Overview

1. Blackbox phase
2. Whitebox phase 1
3. Whitebox phase 2
4. Whitebox phase 3
5. POC plan
   1. execute
   2. refine,reassess,debug
   3.  adapt or repeat ?

### Blackbox 

My approach to a white box Web application penetration test always starts with a **blackbox** portion. This might seem counter-intuitive but I have found that looking at the functioning application gives the best impression of the intended goals and features of the application. Its important not to invest to much time in this part of the assessment, the goal is to get a first impression of the workings of the application and serve as a basis for which parts of the source-code you should look at. It might be tempting to get a certain "payload" or "exploit vector" to work, however this time can much better be invested after having analysed the source code behind this feature.

After the **blackbox** review you should have:

* A list/overview of the exposed features and endpoints for the available roles/users
* Maybe some vulnerabilities or vulnerable endpoints
* A rough idea of the Authentication and Session mechanism
* A rough idea of the languages and frameworks used 
* a rough idea of functionality/features that might be valuable
* a rough idea of functionality/features that might be vulnerable

### Whitebox phase 1

The goal of the first whitebox phase is to **understand** the application. You need to feel conformable navigating the code base and have a rough understanding of where you need to look for specific feature implementations

At the end of **whitebox phase 1** you should know

* What language, frameworks, paradigms are being used
* How the user is Authenticated and Authorized
* How the sessions are being persisted/handled
* How data is being transformed and sanitized
* How data is being stored and retrieved
* A **complete** list of the exposed endpoints and features \(even the ones not used or intentionally hidden in the web application\)
* Have a **clear idea** which functions might be vulnerable and valueble
  * i.e. the list of potential functions from the blackbox has most likely shrunk \(you determined they are not vulnerable because of the code\), however you might have found new interesting functions.

### Whitebox phase 2

By know you have a good idea on how the application functions and you should have a list of vulnerable or at least valuable features/endpoints \(preferably both: vulnerable+valuable\). The goal of this phase is to analyse each of these potential vulnerable or highly valuable functions thoroughly to determine if they can be exploited. 

At the end of **whitebox phase 2** you should know

* Which of the vulnerable/valuable functions can be exploited and which cannot
* Have a rough idea on how to get a full POC for one of these endpoints/features
* You have a better understanding of the vulnerable/valuable functions
  * you might have discovered that certain validations are injected or done by a some library or dependency which is stopping you from successfully exploiting. Make sure to identify this technology and research it for any weaknesses.

If you did find concrete vulnerable features, you might skip phase 3 \(or come back to it later\) and move on to write a full POC for this finding. If you found that all or your features are not exploitable, you move on to phase 3 to see if you can discover other features that are vulnerable.

### Whitebox phase 3

The goal of phase 3 is to look for specific vulnerability types for the language of the application. It might be that you are dealing with a very large code base or simply that the features analysed in phase 2 did not bring any result. In this phase we take a step back from the intuition we build about our web application \(i.e. which functions look interesting and potentially vulnerable\) and try to approach it purely from a systematic side. We look for specific keywords, code patterns, libraries or other vectors that might be hidden in the application

At the end of **whitebox phase 2** you should know

* Identified which of the vulnerabilities the application might be vulnerable to and which ones not!
  * not vulnerable examples: 
    * no native java queries or all paramatirized queries might mean NO SLQ INJECTION
    * full angular application, no unsafeHTML usage, no vulnerable libraries so NO XSS
  * potentially vulnerable examples
    * you found indication of usage of deserialization calls 
    * you find XML parsers are being instatiated
* Identified the locations of potential vulnerabilities
  * analysed them and have a prioritised list of which ones look most promising

### POC phase







