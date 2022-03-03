---

title: Membership Workflow
layout: col-sidebar
permalink: /member_workflow/

---

v2022.03.03

### Membership Workflow
OWASP Membership onboarding is both straightforward and complicated. Straightforward in the sense that a user goes to [Membership](https://owasp.org/membership/) and signs up. 
Complicated in that there are a lot of pieces behind the scenes once that happens. This then, attempts to delineate the high-level happenings from the front-end to the back-end and in-between.

* A user signs up for membership (or renews membership) on the [Membership page](https://owasp.org/membership/), filling out the required data which includes an email address
  The email address is arguably the most important piece of data because, for better or worse, it is the primary id, if you will, of the user. This decision
  was made previously and is done. We can cry over spilt milk later.
* This creates a customer record in Stripe if one does not exist for that email address (we now lowercase the email address because, unfortunately, Stripe allows upper and lowercase 
  for email addresses and treats them differently - this has caused problems in the past)
* Assuming the payment completes, stripe will then (***most of the time***) fire a webhook that calls a back-end function
* The back-end function checks the 'type' of message that was sent from Stripe and, if appropriate, puts the message on the queue for another function to add a membership (renewal or new is the same)
* The next function determines if the message is a completed checkout session or a payment success for a subscription then processes the message as follows, if so:
    * Retrieves the customer, payment information, and the customer's metadata from Stripe
    * Update the customer metadata with membership details
    * Update or create the customer's copper records (Person, Opportunity)
    * Add or update the email and membership information in Mailchimp

So, let's look at what constitutes a membership again:
* A primary email address
* A record in Stripe of the metadata and payment transaction (this records the financial transaction)
* A record in Copper of the metadata and Membership Opportunity (this records the person and creates another record of the membership transaction)
* A record in Mailchimp of the metadata (this is for sending out automated emails, particularly with regard to expiration when it nears)

There are a number of failure points that could happen in this scenario:
* The webhook from Stripe fails to fire (very rare but does happen - this has not been seen, however, in nearly a year)
* The Copper record does not get updated/fails for some reason (rare but can happen due to Copper communication issues)
* The Mailchimp record does not get updated/fails for some reason (also very rare but can happen if, for instance, the email address is unsubscribed or otherwise flagged in Mailchimp)

**Q: What happens if the webhook from Stripe fails?**

**A:** No membership record in Copper or Mailchimp is created. The membership still exists in Stripe.

---

**Q: What happens if the Copper record does not get updated/fails?**

**A:** The record either does not get created or else does not get updated properly. If an exception occurs here, the message returns to queue and will be re-attempted up to 5 times by default. However, failure does not always trigger an exception.

---

**Q: What happens if the Mailchimp record does not get updated/fails?**

**A:** The record either does not get created or else does not get updated properly. This could mean communication does not occur when membership expiration comes up.

---

**Q: What happens if a person does not use the same email address?**

**A:** This is, by far, the most common membership failure in the system. When this happens, the person has multiple memberships - one that is expiring under the old email address and another that is new and most likely triggered creation of new records in Copper.

---

While a robust solution for the second and third item from above would include re-queueing the message on ANY failure and keeping track of where in the process it failed, there is not a good solution for the first and last items. The
last item can be partially resolved by having members use the [Membership Portal](https://members.owasp.org/) to renew their membership (because it auto-populates the [Membership page](https://owasp.org/membership/) with the correct email address)

However, an off-the-shelf membership solution is now in the works which should alleviate all these issues.