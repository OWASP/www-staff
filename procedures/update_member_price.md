---

title: Membership Drive Price Changes
layout: col-sidebar
permalink: /member_pricing/

---

v2023.05.08

Although member pricing is already extremely low, OWASP occasionally runs member discount pricing during 'member drives'. The steps to update
member pricing in the current system is not straight-forward:

### Update Pricing in Azure Functions
The Azure functions is the ONLY place where the price actually will change. Everything else is textual representation of the price. This section assumes
you have Visual Studio installed with Azure tools and know how to deploy these changes. 

* In the Azure Function CreateCheckoutSession, find the membership price you want to change. The pricing lines begin around line 329. These 
amounts are listed in price * 1000 format. So $50.00 is listed as 5000. 
* Change the amount to what you would like to charge. For instance, if you want to change the price of One Year Individual Membership from $50.00 to 
$40.00 then change 5000 to 4000. I highly recommend you add a #comment after the line to indicate what the original price was. Note that there are
lines for OWASP X Year Discounted Membership - these are the amounts for discounted REGIONAL memberships. If you want to discount those as well, you
will need to change their price here too.
* Deploy these changes to Azure.

### Update the Membership page on OWASP Website

* Go to the [membership page in Github](https://github.com/OWASP/owasp.github.io/edit/main/pages/membership.md).
* Add a message, if desired, about the current promotional membership prices (there is an alert div at line 50 for this purpose - just uncomment it 
and change the message to your own message).
* Change the pricing accordingly on lines 225 through 239 or thereabouts.


Once the promotion is over, remember to do the above steps to change everything back. I recommend doing it in reverse order (update the membership page
and then update the Azure functions).
