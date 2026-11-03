## 1. Outage Description

Users were unable to launch the UW-Aero eLAD application, impacting policy quote generation and other business operations.

## 2. Why Did It Happen?

The outage occurred due to a certificate-related issue on the application server, which prevented users from establishing a secure connection to the application. This resulted in application access failures and internal errors, impacting business operations.

## 3. What Could Have Been Done to Avoid This?

Proper validation of certificates after updates, along with post-change application testing, could have helped prevent the issue. Regular monitoring and coordination between the application and infrastructure teams would also have reduced the risk of recurrence.

## 4. Steps Taken and How It Was Fixed

The application, Middleware, Okta, WAF, and Network teams investigated the issue and checked their respective logs. The issue was identified as a certificate-related problem on the server. The Middleware team reinstalled the required certificate on the server, following which the application became accessible. The application team performed AVP in both production and test environments and confirmed that the application was functioning as expected. The incident bridge was closed, and the application team agreed to raise a problem ticket for further RCA and preventive actions.
