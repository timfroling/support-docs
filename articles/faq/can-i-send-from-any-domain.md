---
title: "Can I send from any domain?"
redirect_from: "https://support.sparkpost.com/customer/portal/articles/2457916-can-i-send-from-any-domain-"
description: "Domain Ownership And Control You can send mail through Spark Post from any domain that you or your customers control By verifying your sending domains with Spark Post you're letting us know that you control them and that you authorize delivery from those domains The SPF and DKIM domain verification..."
---

## Domain Ownership And Control 

You can send mail through SparkPost from any domain *that you or your customers control*. By verifying your sending domains with SparkPost, you're letting us know that you control them and that you authorize delivery from those domains. The SPF and DKIM domain verification procedures are the best option here since they also bring deliverability best practice with them. [There are instructions here how to verify your sending domains](https://support.sparkpost.com/customer/portal/articles/1933360-verify-sending-domains). 

## Why Can't I Just Send From Any Domain?

If email services allowed their users to send from any domain or address, anyone could forge email that looked like it came from anyone else.  This opens the door for impersonation, phishing and other illicit acts that we do not wish to perpetuate. We recommend validating your sending domain using SPF and DKIM because they can help with these issues. SPF lets receiving email services validate that mail came from a location authorized by the domain owner. DKIM allows receiving email services to verify that message content was created by an agent authorized by the domain owner and that it has not been altered in transit.

## Sending On Behalf Of Others

You may need to send email on behalf of a 3rd party, often a customer. To achieve this, you could register their domain with SparkPost. They'll need to be complicit since you'll be adding records to their DNS as part of our sending domain verification procedure. If this is not feasible, you could register a subdomain of your own for each customer: e.g. "customer.yourdomain.com".  Then you can mention your customer in the From header: "From: Customer <customer@customer.yourdomain.com>".

## Use Reply-To As Needed

You also have full control of the Reply-To header in your messages - you can use any email address, *including using domains which are not valid sending domains*. In this case you could set Reply-To to a customer domain to allow them to handle human replies to your messages and to offer a little more customer branding if you are sending from your own domain on their behalf.