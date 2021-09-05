# IA Lab Captive Portal

## Authenticating through the lab captive portal

This is required for general Internet access as long as the vApp has been created with connection to networks that are connected to the Internet.

1. Make sure that your vApp is connected to an organization network
  * Example: vCloud\_Internet, vCloud\_CSC436
2. Check to make sure all interfaces have correct addressing
3. To redirect to the captive portal, browse to a non-HSTS site
   1. [http://captive.ialab.dsu.edu/](http://captive.ialab.dsu.edu/), [https://www.noaa.gov/](https://www.noaa.gov/), [https://captive.apple.com](https://captive.apple.com/), and [http://neverssl.com](http://neverssl.com) are all good choices to try.

For more information on HSTS, check out [HTTP Strict Transport Security Cheat Sheet - OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
