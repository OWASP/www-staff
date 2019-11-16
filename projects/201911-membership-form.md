---

title: Membership Form
layout: full-width

---

# Membership Form

## Overview

As part of the OWASP website migration, we will creating a new membership form and process that will use Stripe as a back end. Following the successful test of the Donation Form, this project should be relatively easy with some small differences from that project. Once implemented, we will unwide our dependency on Fontiva and will migrate to using Mailchimp as a "light" member CRM with all history transaction data stored in Stripe.

## Goals
1. Securely host a form oun our public github instance and collect donations
2. Put form into production as of 22-November
3. Move data from successful Sripe traction into Mailchimp
4. Automate creating OWASP email address

## Milestones
- [x] 2019-10-24, Kickoff call [Mike]
- [x] 2019-10-28, Contract signed and project underway, [Mike]
- [x] 2019-11-08, Onboard Simon to Azure and Stripe, [Harold]
- [x] 2019-11-10, Wireframe sent [Membership Form wireframe](/www-staff/files/membership-wireframe.pdf), [Mike] 
- [ ] 2019-11-19, Form completed for demonstration, [Simone]
- [ ] 2019-11-21, Regression testing complete, [Harold]
- [ ] 2019-11-22, Project Complete ready for deployment, [Harold]
- [ ] 2019-12-11, Deploy to new website in production, [Harold]

## Leadership

* [Harold Blankenship - Lead](mailto:Harold.blankenship@owasp.com?subject=Project:%20Donation%20Form)
* [Mike McCamon](mailto:mike.mccamon@owasp.com?subject=Project:%20Donation%20Form)

## Workflows
### New/Renew Membership
1. Visitor clicks on a Join link someplace in OWASP Universe
   1. Page on website
   2. Link from an email
   3. Link from a partner
2. Join form MAY receive email address from an inbound link
   1. This feature is designed for renewal emails that will include the user email
3. Membership page has:
   1. Country drop down
      1. js will update one year price to $20 if visitor selects country in lower 1/2 of WW GNP
      2. js will hide two year and lifetime membership options
   1. Company name
   1. Check box to indicate "Set Membership to Auto-Renew"
   4. Check box to "Join the OWASP Mailing List"
   4. Small legal copy about GDPR, membership business emails (they are not opt-in), and truthful representation to manage fraud. 
4. Click "Join"
4. All form data and transaction stored into Stripe
5. Light Integrations move data
6. After completing integrations, update field in Stripe that donation was processed through integrations.

### Change Billing Info
1. User visits new 'Subscription Management' page of OWASP site
2. User inputs email address into form field
3. User submits form and sees a message that says if an active subscription was found, a link to manage it has been emailed to the address.  This message appears whether or not a subscription was found.
4. If a subscription was found with a matching email address, an email is sent to it that contains a unique link to Stripe Checkout where the payment information can be updated.
  
## Budget
Hourly rate expected to be less than $1,500.

## Project Links
* [Donation Form wireframe](/www-staff/files/membership-wireframe.pdf)

