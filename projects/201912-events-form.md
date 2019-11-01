---

title: Events Form
layout: full-width

---

# Events Form

## Overview

As part of the OWASP website migration, we will creating a new Events form that will use Stripe as a back end. This should be a simple form that is hosted on the website and will serve as the prmiary e-commerce path for all OWASP Global and Regional events replacing Eventbrite for (1) hosting secure forms on github, (2) presenting and then selecting multiple SKUs from a single Product ID as in Training Class A for Event X and Early Bird ticket for Event X, (3) 2-3 aggregate online reports, (4) validate Strike can manage inventory of SKUs, and (5) integrating Stripe form activities with light integrations with other key data in the OWASP ecosystem.

## Goals

1. Securely host a form oun our public github instance and collect event registrations
1. Designed and built for re-use on up to 15 events per calendar year (Product ID/SKU)
2. Put form into production as of 20-December-2019
3. Move data from successful Sripe tranaction into Mailchimp
3. Recognize donors and the projects/chapters they support

## Milestones
- [ ] In an unordered list (billeted) list major milestones in chronological order
- [ ] Use the syntax of 2019-01-19, Milestone name, [Name of Owner]
- [x] When milestones are completed, mark them with an "x"
- [ ] A milestone isn't everyone’s to-do list, it is the high level tasks of the project
- [ ] If you have more than 30 milestones, you’re being too granular
- [x] 2019-09-22, Action item completed, [All]
- [x] 2019-09-30, You can leave the box UNCHECKED if not completed but you must edit page to change state, [All]
TBD

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
1. Visitor clicks on a event link someplace in OWASP Universe
   1. Page on website
   2. Link from an email
   3. Link from a partner
2. Event page has:
   1. Popup to capture email for shopping cart abandomment and returning to form
      1. If returning it woudl restate the cart in the previous state
   1. Collect money in foreign currencies
   1. Introductory copy about the Event
   1. Listing of SKUs for the Product
      1. If a SKU has an inventory, show SOLD OUT or quantity remaining
      2. Use checkboxes to select SKUs ( v1.0 will not allow multiple units purchased)
   1. Text field for DISCOUNT CODE
   1. Drop down or Security Industry Experience [Beginner/Intermediate/Advanced]
   1. Drop down for Persona [Defender/Builder/Breaker]
   1. Check box for Photo Release
   1. Text field to indicate dietary restrictions
   4. Check box to "Join the OWASP Mailing List"
   4. Small legal copy about refunds and LINK to "Invoice me instead of paying online" 
3. Click "Donate" and given Stripe transaction form
4. All form data and transaction stored into Stripe
5. Light Integrations move data
   1. Registrant email address will be added to Mailchimp adding the ProductID tag to the contact
      1. Stripe will handle sending a receipt
      2. Mailchimp will handle sending Registrant Curriculum
6. After completing integrations, update field in Stripe that donation was processed through integrations.
7. Online Reports
   1. Public list of Product SKUs with number sold and revenue. Nice to have include Inventory Remaining
   2. Dietary Report
   3. CSV export for badges
   4. [Nice to have] Live link with Boomset for badge
   
## Questions
1. Collect email popup we can do ambandoned shopping cart and "return to complete form"
2. Group discounts will be handled with an invoice - not online

## Budget

## Project Links

Use this section for important links for projects/events that visitors will need. For instance, if this is an event, links to CFT, CPT and registration is handy If there is a microsite, that would be good to link to as well 
* [Example link to Google](https://google.com)
* [Example relative link to Blank Template Page](/www--staff/Projects/202001-template)

