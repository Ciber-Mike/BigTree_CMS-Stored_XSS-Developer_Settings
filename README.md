# BigTree_CMS-Stored_XSS-Developer_Settings
**Software Link**: BigTree CMS [https://www.bigtreecms.org/download/core/]
**Author**: Miguel Ángel Ruiz
**Description**: BigTree CMS version 4.5.7 is affected by a Stored Cross-Site Scripting (XSS) vulnerability that allows an attacker to inject malicious code into the developer settings panel, enabling them to execute stored code when accessing the /site/index.php/admin/developer/settings resource.

---
# Proof of Concept

1. A setting is edited within the developer menu, injecting a payload (JavaScript code) into the `ID` field."
![Payload inyected](https://github.com/Ciber-Mike/BigTree_CMS-Stored_XSS-Developer_Settings/assets/146454370/bf0b04b7-3ccd-4969-9b4f-34d8a5792998)


2. When the user accesses the `/site/index.php/admin/developer/settings` resource, this stored code is executed.
![Exploited XSS](https://github.com/Ciber-Mike/BigTree_CMS-Stored_XSS-Developer_Settings/assets/146454370/1528f833-94ab-41c7-a18f-a99758dedaa9)

## Payload:
```js
<><img src=1 onerror=alert('XSS_Stored_ID')>
```

---
## References
https://owasp.org/Top10/es/A03_2021-Injection/

https://owasp.org/www-community/attacks/xss/
