---

title: Mailchimp as CRM
layout: full-width

---

# Mailchimp as CRM

## Overview

As part of the website migration, the OWASP Foundation is also be migrating our membership database to MailChimp. There are a variety of reason for this change (1) ongoing data syncrhonization issues, (2) problematic SalesForce implmentation needs complete retool for continued use, (3) cost of third party softare to manage members in SalesForce is ~$10,000 per year, and (4) nearly all email to members is sent through Mailchimp. The audience on Mailchimp will be **OWASP-main** and members can be identified by the membership-end-date being after today's date.

This project will consolidate the OWASP Foundation membership infomation into MailChimp. Historical member payments will be maintained as a log in Stripe and work item before eo2019 will be to import historical membership transaction data into Stripe.  The unique identifier for members will their personal email address.

## Goals

1. Include top-level goals of the project in an ordered list
2. Give thought to the ordering of goals. Revenue, attendance, launch date
3. Make sure goals are measurable from undisputed source

## Leadership

* [Mike McCamon](mailto:mike.mccamon@owasp.com?subject=Mailchimp%20CRM)
* [Harold Blankenship](mailto:harold.blankenship@owasp.com?subject=Mailchimp%20CRM)

## Schema for MailChimp

```
email
name
company
country
postal-code
membership-start-date
membership-end-date
membership-type [one, two, lifetime, honorary, student]
source [memberform-api, donateform-api, gdpr-form, {import list source}]
```

The Membeship form will either creates a new list member OR just updates these fields when there is a renewal

```
company
country
postal-code
membership-end-date {current-date+365 days}
membership-type [one, two, lifetime, honorary]
source [memberform-api, {import list source}]
```
