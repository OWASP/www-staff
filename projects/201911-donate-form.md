---

title: Donation Form
layout: full-width

---

# Donation Form

## Overview

As part of the OWASP website migration, we will creating a new Donation form that will use Stripe as a back end. This should be a simple form that is hosted on the website and will serve as a proof of concept for (1) hosting secure forms on github, (2) test the viability of Stripe for payment processing, and (3) integrating Stripe form activities with light integrations with other key data in the OWASP ecosystem.


## Goals

1. Securely host a form oun our public github instance and collect donations
2. Put form into production as of 15-November
3. Recognize donors and the projects/chapters they support

## Milestones

* 2019-10-24, Kickoff call [Mike]
TBD

## Leadership

* [Harold Blankenship - Lead](mailto:Harold.blankenship@owasp.com?subject=Project:%20Donation%20Form)
* [Mike McCamon](mailto:mike.mccamon@owasp.com?subject=Project:%20Donation%20Form)

## Workflow
1. Visitor clicks on a donate link someplace in OWASP Universe
   1. Page on website
   2. Link from an email
   3. Link from a partner
2. Donation page has:
   1. Introductory copy about "Why Donate to OWASP Foundation"
   1. pre-set donation amounts of $10, $25, $50, $100 and other. 
   2. Check box to indicate "Make a Recurring Monthly gift"
   3. Check box to indicate attribution, "Publicly list me as a supporter of [referring url title]"
   4. Check box to "Join the OWASP Mailing List"
   4. Small legal copy that the gift is unrestricted and can be used for any purpose. 
   5. {Optional] Links/Info about how the Foundation uses gifts
3. Click "Donate" and given Stripe transaction form
4. All form data and transaction stored into Stripe
5. Light Integrations move data
   1. Donor email address will be added to Mailchimp with the date of the donation in mailchimp.first_donation_date
     1. Mailchimp will handle sending a receipt
     2. Mailchimp will handle sending New DOnor Curriculum
   1. If donor selected "Add me to mailing list"
     1. The text ", donor" will be appended to Mailchimp.type
     2. Boolean for "marketing_emails" in Mailchimp will be set to true
   2. If donor slected "Publicly list me.." - a pull request will be created for the page target project/chapter page of tab_onlinedonors.md that will add the name to an unordered list for that page.
  
## Budget

## Project Links

Use this section for important links for projects/events that visitors will need. For instance, if this is an event, links to CFT, CPT and registration is handy If there is a microsite, that would be good to link to as well 
* [Example link to Google](https://google.com)
* [Example relative link to Blank Template Page](/www--staff/Projects/202001-template)

