---
title: "SMTP and REST API Injection Best Practices for Improved Performance"
redirect_from: "https://support.sparkpost.com/customer/portal/articles/2429473-smtp-and-rest-api-injection-best-practices-for-improved-performance"
description: "Spark Post wants to make sure all of our customers have the best sending experience through our service We have a few recommendations to ensure you are injecting in the most efficient manner and to optimize overall message throughput Sending via the Transmission REST API We recommend that you send..."
---

SparkPost wants to make sure all of our customers have the best sending experience through our service.  We have a few recommendations to ensure you are injecting in the most efficient manner and to optimize overall message throughput.

## Sending via the Transmission REST API

We recommend that you send via the Transmission REST API, if possible. Overall the REST API is more efficient than SMTP and requires less resources on the client side.

* Keep the size of the transmission to approximately 50MB.  This refers to the total size of the JSON used for transmission, including any substitution data.
* Use concurrent connections by having multiple transmissions running in parallel.
* Send smaller concurrent batches.  Sending 10 transmissions of 2,000 recipients each is more efficient than sending 4 transmissions of 5,000 recipients.
* For large bulk mailings of 100,000 or more, keep the maximum number of recipients to 10,000 and the minimum number of recipients to 2,000 per transmission call.
* Limit the concurrent connections to a maximum of 10\.  (For SparkPost Elite customers, please contact your TAM for guidance on the number of concurrent connections.)
* Set API timeout to 300 seconds.  
* On timeout or any 5XX error the best practice is to retry.

## Sending via SMTP

Follow these best practices in order to optimize SMTP injection rates (and overall sending speed):

* Use concurrent connections by having multiple batches running simultaneously - use up to 10 connections at a time.  Having multiple connections open and running allows more messages to be sent in a shorter period of time.  (For SparkPost Elite customers, please contact your TAM for guidance on the number of concurrent connections.)
* Keep the TCP connections open between messages.  Closing and opening connections on each message is much less efficient and can slow performance.
* Ensure your SMTP client has pipelining enabled, to reduce the roundtrip delay on some SMTP commands.

## General Message Size Considerations

* For optimal deliverability, the total size of each message should not exceed 100kb.
* For messages with inline images and attachments, keep the total message size to less than 20MB - total size limit includes the **body** PLUS **images** PLUS **attachments**

Need help or advice with technical issues?  Check out our community Slack channel at [slack.sparkpost.com](http://slack.sparkpost.com/) or [submit a support request](https://support.sparkpost.com/customer/portal/emails/new?email[subject]=Injection%20Best%20Practices).