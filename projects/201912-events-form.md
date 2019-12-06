---

title: Events Form
layout: full-width

---

# Events Form

## Overview

As part of the OWASP website migration, we will creating a new Events form that will use Stripe as a back end. This should be a simple form that is hosted on the website and will EVENUTALLY serve as the prmiary e-commerce path for all OWASP Global and Regional events replacing Eventbrite for (1) hosting secure forms on github, (2) presenting and then selecting multiple SKUs from a single Product ID as in Training Class A for Event X and Early Bird ticket for Event X, (3) 2-3 aggregate online reports, (4) validate Stripe can manage inventory of SKUs, and (5) integrating Stripe form activities with light integrations with other key data in the OWASP ecosystem.

## Goals

1. Securely host a form on our public github instance and collect event registrations
1. Designed and built for re-use on up to 15 events per calendar year (Product ID/SKU)
1. Stripe is the single authoritive source of pricing, inventory, and discount code truth
2. Put form into production as of January 24, 2020
3. Move data from successful Sripe tranactions into Mailchimp
3. Light reporting on attendance metrics
4. Develop Slack bot so that common queries can be done through Slack

## Milestones
- [x] 2019-11-01, Identify resource to develop this form/project, [Mike]
- [x] 2019-11-28, Spec out workflow for visitors, [Mike]
- [ ] 2019-12-31, Wireframe of Event Form, [Mike]
- [ ] 2020-01-03, Test Event as SKU in Stripe for dev effort, [Mike]
- [ ] 2020-01-10, Beta version of Event Form Ready for testing, [Simon]
- [ ] 2020-01-17, Relecase Candiate of Form ready for regression testing, [Simon]
- [ ] 2020-01-23, Launch form with Global AppSec - Dublin as first product, [Harold]
- [ ] 2020-01-31, Release Candidate of Forms and Slack bot, [Simon]
- [ ] 2020-02-07, Project Complete, [Harold]

## Leadership

* [Harold Blankenship - Lead](mailto:Harold.blankenship@owasp.com?subject=Project:%20Events%20Form)
* [Emily Berman - Customer](mailto:emily.berman@owasp.com?subject=Project:%20Events%20Form)
* [Mike McCamon](mailto:mike.mccamon@owasp.com?subject=Project:%20Events%20Form)

## Workflow
1. Product and SKUs listings created in Stripe
   1. Set prices in foreign currencies
   1. Deal with VAT issues
2. Discount codes created in Stripe
   1. Can we set limits for number of uses of a particular Discount Code.
   2. need to determine how we handle Member Discounts
1. Visitor clicks on a event link someplace in OWASP Universe
   1. Page on website
   2. Link from an email
   3. Link from a partner
2. Event page has:
   1. Popup to capture email for shopping cart abandomment and returning to form (Nice to have)
      1. If returning it woudl restate the cart in the previous state
   1. Collect money in foreign currencies
   1. Introductory copy about the Event
   1. Listing of SKUs for the Product
      1. If a SKU has an inventory, show SOLD OUT or quantity remaining
      2. Use checkboxes to select SKUs ( v1.0 will not allow multiple units purchased)
   1. Text field for DISCOUNT CODE
   1. Drop down or Security Industry Experience [Beginner/Intermediate/Advanced]
   1. Drop down for Persona [Defender/Builder/Breaker]
   1. Check box for Photo Release (Detault is ON)
   1. Text field to indicate dietary restrictions
   4. Check box to "Join the OWASP Mailing List"
   4. Small legal copy about refunds
   4. Link to "Invoice me instead of paying online" that goes to (New) WuFoo Form
3. Click "Purchase" and given Stripe transaction form
4. All form data and transaction stored into Stripe
5. Light Integrations move data
   1. Registrant email address will be added to Mailchimp adding the ProductID tag to the contact
      1. Stripe will handle sending a receipt
      2. Mailchimp will handle sending Registrant Curriculum
7. Online Reports
   1. Public list of Product SKUs with number sold and revenue. Nice to have include Inventory Remaining
   2. Dietary Report
   3. CSV export for badges
   4. [Nice to have] Live link with Boomset for badge
   
## Slack Bot Requirments
1. /event-lookup
   1. Responds with a list of events from now-30 days through "end of time" that include Name (as URL to online report from above), total-Number-of-registrats
1. /event-history 
   1. Same as event-lookup but responds with ALL historical events
2. /event-attendee {string}
   1. responds with any event registrations where first-name, last-name, company, or email-address CONTAINS {string} sorted in last-name/first-name ascending order. First line of response includes email as mailto URL
      1. List should include Event Name, Product Purchased, Amount Paid, Discount code used and StripeTransactionID
   2. responds with "None Found" if no records found in Stripe
   3. If result set is > 100 records add "More..." link as button to retrieve more records
3. /event-attendee-details {StripeTransactionID}
   1. Responds with all data from that Stripe Transction and first line of response includes email as mailto URL

## Questions
1. Collect email popup we can do ambandoned shopping cart and "return to complete form"
2. Group discounts will be handled with an invoice - not online

## Budget

$5,000

