+++
title = "The Windows Modern Standby Conundrum: When Sleep Isn't Really Sleep"
date = 2024-07-12T02:57:06+05:30
draft = false
tags = ["Windows", "Modern Standby", "Power Management"]
categories = ["Tech Tips", "Troubleshooting"]
+++

Have you ever put your laptop to "sleep" only to find it wide awake later? You're not alone. Modern Windows machines have a feature called Modern Standby that has changed the game - and not always for the better.

## The Unexpected Wake-Up Call

Recently, I experienced a rude awakening: my Windows 11 laptop's fans were running at ***FULL SEND*** despite the lid being closed. This wasn't an isolated incident. Previously, I've placed a fully charged laptop in my bag, only to retrieve it later, hot to the touch and with a depleted battery.

## What's Really Happening?

The culprit? Modern Standby. This feature replaces traditional sleep mode with a low-power state that maintains network connectivity. While it sounds promising, offering benefits like:

- Faster wake-up times
- Ability to charge external devices when the lid is closed
- Background Windows updates during idle periods

...it may not be what every user wants or expects from a "sleep" mode.

## The Dilemma

Here's the kicker: you can't simply disable Modern Standby. Microsoft and OEM vendors have patched workarounds that attempted to restore the old sleep behavior through registry edits. The firmware no longer supports these alternative sleep states.

## How to Check Your Sleep Options

To see what sleep states are available on your system, open Command Prompt and type:

```
powercfg /a
```

This command will display all available sleep states for your device.

In my case, the machine only supports S0 (Modern Standby), while S1, S2, and S3 sleep states are unavailable.

![powercfg /a](/posts/2/1.png)


## Potential Workarounds

If your system supports other sleep states, you can look up YouTube tutorials on how to disable Modern Standby. However, if you're in the same boat as me, here's a workaround:

1. Navigate to `Control Panel > Hardware and Sound > Power Options`
2. Click on "Choose what closing the lid does"
3. Set "When I close the lid" to "Hibernate" instead of "Sleep"

![Choose what closing the lid does](/posts/2/2.png)
![When I close the lid" to "Hibernate](/posts/2/3.png)

This should prevent your machine from staying active while "sleeping," allowing you to resume from where you left off. The downside is that waking up becomes slower, especially if Windows isn't booting from an SSD.



## The Shutdown Surprise

While we're on the topic of features not working as expected, it's worth noting that the "Shutdown" option doesn't completely power down your machine either. Most modern Windows devices ship with "Turn on fast startup" enabled, which preserves previous machine states for faster booting.

Interestingly, it's the "Restart" option that truly starts the machine from a fresh state. For this reason, I disable fast startup on every machine I use. With modern SSDs, a clean shutdown shouldn't take too long anyway.