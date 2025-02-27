---
title: 'Publishing Prav on the Play Store'
date: 2025-02-25T20:23:55+05:30
params:
  author: 'Vishnu Sanal T'
keywords: ["prav", "open-source", "play-store", "android", "volunteer", "community"]
description: "Story of Volunteering to Publish Prav App on the Google Play Store"
---

Story of Volunteering to Publish [Prav App](https://prav.app/) on the Google Play Store

Hmm, you might be thinking, What is there to write a blog post about publishing a simple app on the Play Store? Huh?! Well, the story of a long, boring and _very_ frustrating ordeal follows.

So, I was walking around with my friends on [IndiaFOSS 2024](https://fossunited.org/indiafoss/2024) and stumbled upon Prav's stall and the team. A native Android project immediately struck my attention. Badri then mentioned that Prav is looking for a volunteer to help them publish the app on the Play Store. I jumped right in!

Badri had trouble sending me the links for me to join. The platforms we used were _mutually exclusive_. ;) I joined the Codema instance and forgot to join the XMPP chatrooms. ://) TBH, I didn't even know what it was or how it worked. xD I later joined the XMPP rooms, and we started the discussions on how to publish Prav on Google Play.

The first step came with a blocker, whether to choose an organization account or a personal account. Creation of an organization account needed a DUNS ID, which we don't have, a personal account came with the limitations of it depending on a single developer & their details being shown in public. Joice tried a lot to get the DUNS ID, but then we gave up waiting, and we decided to go with a personal account.

Next was the payment, which must be easy; just swipe some card for $25, and you're done, huh? Wait, no! My card got blocked whilst doing this for some reason; Joice was able to complete it from his card, and we were in! Joice also sponsored the account fee.

I thought we were in, and we could do a production release now. And, boy, I couldn't have been any wrong!

Play Store warned us with:

> > If you have a newly created personal developer account, you must run a closed test for your app with a minimum of 12 testers who have been opted-in for at least the last 14 days continuously. When you meet these criteria, you can apply for production access on the Dashboard in Play Console so that you can ultimately distribute your app on Google Play. When you apply, you must answer some questions to help us understand your app, its testing process, and its production readiness.

Really bro? Am I in for publishing a new app, or with a marriage proposal?!

Anyway, we complied; we got sufficient testers from Prav community members, their & my friends, family, etc. Now to create the release... Apart from providing the usual metadata, AAB file and stuff, we had to record some videos demonstrating the usage of "sensitive permissions",  i.e., different `FOREGROUND_SERVICE`'s. ;__; We needed them for instant messaging, voice calls, and video calls; this took a while for me to figure out though. :D

And finally, we ran the internal testing track for 14 days and finally got the production access. Yay!

Now, let's just create a production release and forget about it, right? Wrong! :-/

I was able to create the production release without any issues but then came rejection stating:

> > You didn't provide an active demo/guest account or a valid username and password which we need to access your app.

Okay, so now we have to set up a dummy account. The solution to this was to do some setup on the server side. Hmm, "enough of client-side; now mess with some server-side code." I had zero idea what to do, though! Ravi quickly gave me access to the server, and Praveen guided me through the process. I tested with a dummy account, found it to be working, and re-requested a review from Google.

Now, finalllyyyyyy, we made it through this time! Yayy! :)

See, do you now get what I said in the beginning?! This whole stuff took around 6 months... We are all volunteers, with our stuff beneath us, but damn, six months is a very long time to get an app *just published*; mind you, we had it already built and ready to go...!

Is this blog interesting? Share with someone. Since you are here, you must be a FOSS enthusiast; if yes, let's get connected! Or, if you're just surfing around here too, just ping me! I love talking to new people. :)

Find me on [GitHub](https://github.com/VishnuSanal), [Twitter](https://twitter.com/VishnuSanalT), [Mastodon](https://fosstodon.org/@VishnuSanal), or [LinkedIn](https://www.linkedin.com/in/vishnu-sanal-t/).