---

title: Donation Form
layout: full-width

---

# Donation Form

## Overview

As part of the OWASP website migration, we will creating a new Donation form that will use Stripe as a back end. This should be a simple form that is hosted on the website and will serve as a proof of concept for (1) hosting secure forms on github, (2) test the viability of Stripe for payment processing, and (3) integrating Stripe form activities with light integrations with other key data in the OWASP ecosystem.

Current working demo at [https://www2.owasp.org/donate](https://www2.owasp.org/donate) Form will handle &title and &currency parameters

## Goals

1. Securely host a form oun our public github instance and collect donations
2. Put form into production as of 15-November
3. Move data from successful Sripe traction into Mailchimp
3. Recognize donors and the projects/chapters they support

## Milestones

- [x] 2019-10-24, Kickoff call [Mike]
- [x] 2019-10-28, Contract signed and project underway, [Mike]
- [x] 2019-11-08, Onboard Simon to Azure and Stripe, [Harold]
- [x] 2019-11-10, Wireframe sent [Donation Form wireframe](/www-staff/files/donation-wireframe.pdf), [Mike] 
- [x] 2019-11-22, Form completed for demonstration, [Simon]
- [ ] 2019-12-19, Regression testing complete, [Harold]
- [ ] 2019-12-23, Project Complete ready for deployment, [Harold]
- [ ] 2019-12-23, Deploy to new website in production, [Harold]

## Leadership

* [Harold Blankenship - Lead](mailto:Harold.blankenship@owasp.com?subject=Project:%20Donation%20Form)
* [Mike McCamon](mailto:mike.mccamon@owasp.com?subject=Project:%20Donation%20Form)

## Workflow
1. Visitor clicks on a donate link someplace in OWASP Universe
   1. Page on website
   2. Link from an email
   3. Link from a partner
2. Donate button will receive two parameters from donate link
   1. Title of the page
   2. Repo path (for light integrations)
2. Donation page has:
   1. Introductory copy about "Why Donate to OWASP Foundation"
   1. pre-set donation amounts of $10, $25, $50, $100 and other. 
   2. Check box to indicate "Make a Recurring Monthly gift"
   3. If there is a Page Title passed to the page then 
      1. Check box to indicate attribution, "Publicly list me as a supporter of [referring url title]"
      1. Otherwise, do not show this field since this inbound link was from a non-attributable source
   4. Check box to "Join the OWASP Mailing List"
   4. Small legal copy that the gift is unrestricted and can be used for any purpose. 
   5. [Optional] Links/Info about how the Foundation uses gifts
   6. [Optional] Tab for selecting one of 2-3 currencies.
3. Click "Donate" and given Stripe transaction form
4. All form data and transaction stored into Stripe
5. Light Integrations move data
   1. Donor email address will be added to Mailchimp with the date of the donation in mailchimp.first_donation_date
      1. Stripe will handle sending a receipt
      2. Mailchimp will handle sending New DOnor Curriculum
   1. If donor selected "Add me to mailing list"
      1. The text ", donor" will be appended to Mailchimp.type
      2. Boolean for "marketing_emails" in Mailchimp will be set to true
   2. If donor slected "Publicly list me.." - a pull request will be created for the page target project/chapter page of tab_onlinedonors.md that will add the name to an unordered list for that page.
6. After completing integrations, update field in Stripe that donation was processed through integrations.

## Added Feature: Handling (Optional) Restricted Gifts
1. Donation form includes another check box field "restricted" that by default is HIDDEN and not required input.
 1. If the query string includes "restricted=yes" the field is shown CHECKED with "I understand this restricted gift amount is net 15% administration costs and unspent restricted gift balances become unrestricted at the end of each calendar year."
   1. When Restricted, to submit the form:
     1. The amount MUST be more than $1,000
     2. The checkbox MUST be checked.
 2. State of this field is saved in Stripe as "yes" when checked, NULL when empty.

## Mailchimp CRM Insert
```
email
name
country
postal-code
~~membership-start-date~~ {unused}
~~membership-end-date~~ {unused}
~~membership-type~~ {unused}
source [donateform-api]
```

  
## Budget
Hourly rate expected to be less than $1,500.

## Project Links
* [Donation Form wireframe](/www-staff/files/donation-wireframe.pdf)

