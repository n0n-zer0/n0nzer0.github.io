# Blackbox test

## Blackbox review

* Start your favourite proxy \(BURP/ZAP\) + Open your browsers development TAB
* Explore **Unauthenticated** features/endpoints
  * Any features that take user-input ?
    * registration ?
    * comments ?
  * Any enumeration/information ?
    * Can you view user-profiles ?
* Explore **Authenticated** features/endpoints
  * What can Authenticated user do that unauthenticated cannot ? \(Available features ?\)
    * File upload ? \(profile picture etc ?\)
  * client side validations ?
* Explore **Elevated privileges \(Admin or other user roles\)**
  * available features ?
    * import/export ?
    * templates ?
    * commands ?
    * SQL / Query ?
    * ZIP, File manipulation ?
* Analyse Session mechanism
  * Session variable ?
    * cookie ?
      * flags ?
    * token ?
      * stored where ? \(local-storage / session-storage\)
* Analyse Authentication mechanism \(see: [https://cheatsheetseries.owasp.org/cheatsheets/Authentication\_Cheat\_Sheet.html](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)\)
  * Does it "leak"information ? \(i.e. acknowledge user accounts exists in the error responds\)
  * What is the password policy ?
  * is username/account name uniqueness gueranteed ?
    * server side as well ?
  * Account lock-out ? \(i.e. are accounts locked after a number of tries ?\)
  * Account password reset functionality ?
  * Remember me functionality ?
  * Authentication protocols used ?
    * oauth ?
    * openID
    * saml
    * fido
* Analyse client source-code \(open Development view, SOURCES TAB in CHROME\)
  * What files are loaded ? from where ?
  * Any collection of endpoints ?  controllers ? Actions ?
  * What Framework/tech-stack is being used ?
  * Any interesting Developers comments ?
* Analyse Web traffic \(BURP or ZAP & open Development view, NETWORK TAB in CHROME\)
  * Anything interesting ?
  * Any non HTTP traffic \(websockets etc\) ?
* Do some basic blackbox testing \(**+- 30 min, 1h MAX**\)
  * SQL injections
  * XSS payloads
  * File upload bypass
  * File inclusion / Dir traversing
  * Try to trigger a ERROR or application Exception!
    * any debug information ?
    * stacktrace ?
  * Find any debug features  or test functionalities ?

