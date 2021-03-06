---
title: "SMTP Engagement Tracking"
redirect_from: "https://support.sparkpost.com/customer/portal/articles/2539063-smtp-engagement-tracking"
description: "You can control your account’s default setting for tracking of messages submitted via SMTP to be enabled or disabled The option is in the Account SMTP Relay page of your Spark Post user interface Before you make a selection the system default Disabled will apply to your account This is..."
---

You can control your account’s default setting for tracking of messages submitted via SMTP to be enabled, or disabled.

The option is in the Account / SMTP Relay page of your SparkPost user interface:

![](media/smtp-engagement-tracking/engagement_tracking_original.jpg)

Before you make a selection, the system default (Disabled) will apply to your account.  This is why there’s no radio button visible until you make a selection.

If you have tracking disabled, then you won’t see “open” and “click” events in your event stream (whether via Webhooks, or via the Message Events API). 

What this is actually controlling is whether SparkPost will ‘wrap’ the links in your messages with a Tracking Domain URL, so that your recipients’ browsers will redirect - briefly - via our servers before the final destination.  This allows us to count your recipients’ clicks.

Since 2<sup>nd</sup> December 2015, the system default is “disabled” for messages injected via SMTP – see [Change Log](https://support.sparkpost.com/customer/en/portal/articles/1936102-change-log)

## Related Articles

You can also control event tracking from your upstream message source, via our “SMTP API”, as [described here](https://developers.sparkpost.com/api/smtp-api).

You can register [Custom Tracking Domains](https://support.sparkpost.com/customer/en/portal/articles/2139249-enabling-multiple-custom-tracking-domains) for better message alignment that can improve deliverability.