---
title: "DialogMusicPlayer: the whole story"
date: 2024-02-17T23:10:11+05:30
author: Vishnu Sanal T
keywords: ["DialogMusicPlayer", "DMP", "music", "simple", "minimal"]
description: "Why did I build DialogMusicPlayer, and how's it going?"
---

[DialogMusicPlayer](https://github.com/VishnuSanal/DialogMusicPlayer) is a simple and minimal music player dialog. It was built out of my frustration with my device’s stock music player requesting unnecessary permissions just to play a music file. The basic version was built within a day on a skeletal level. I thought of DMP as a simple project that would only be used by me on my device. I made the code open source & left it on GitHub.

Some of the members of the project’s discussion group spotted this new project & tried it for themselves. They reported some issues with the application. I quickly found a solution and released a fix. Now that I fixed the critical issues, one of them [proposed](https://gitlab.com/IzzyOnDroid/repo/-/issues/192) for the app to be included in the [IzzyOnDroid](https://apt.izzysoft.de/fdroid/index/info) repository (a repository by an F-Droid maintainer for the apps that are not "fully compliant" with the main repo). The proposal got accepted, and DMP was live on IzzyOnDroid. I then got some new issues reported requesting new features, and it was then that I started taking the project seriously. Then, I asked for help from a couple of my friends to help me with the design and improve it. I polished the design as per their awesome design. Now, I wanted it to be published in the [F-Droid](https://f-droid.org/) main repository, [requested packaging](https://gitlab.com/fdroid/rfp/-/issues/1994), got accepted; we were live on F-Droid! I still remember getting excited with [the comment Andreas (Izzy) left](https://gitlab.com/fdroid/fdroiddata/-/merge_requests/10419#note_814165706) welcoming us to F-Droid.

Meanwhile, almost a month after DMP got rolled on F-Droid’s repo, I discovered a major issue in the app that was caused by a mistake of mine. I have written a separate blog on that [here](https://vishnusanal.github.io/posts/when-code-made-me-feel-like-a-failure/).

I carried on working on the app., mostly fixing issues & working on small features once in a while -- viz., playback speed, remembering where you left off, repeat, rewind/seek etc. And life was good! However, a major issue that was still troubling the app was the integration with Android’s `MediaSession` API. I struggled with this for weeks, if not months. I looked into documentation (that felt complicated) and blog posts/tutorials (that were outdated). Furthermore, I kind of left it the way it was for a while and continued finding workarounds until I decided that I should fix this issue once and for all. I created a new project from scratch & implemented a simple music player by referring to the documentation & other sources. This worked, after almost a year! Once this was stable, I migrated this new project into DMP’s codebase piece by piece, fixing the issues that appeared along the way. Remember the sweet feeling of fixing issues you had for a while? The happiness of deleting code that you used to workaround something "unfixable", now that you found a new way to do it? Finally, [v2.0.0 was released](https://github.com/VishnuSanal/DialogMusicPlayer/releases/tag/v2.0.0) with this new architecture.

DMP got a UI overhaul on the very next [v2.1.0 release](https://github.com/VishnuSanal/DialogMusicPlayer/releases/tag/v2.1.0) too.

Now, DMP is live on [Google Play](https://play.google.com/store/apps/details?id=phone.vishnu.dialogmusicplayer) and [F-Droid](https://f-droid.org/packages/phone.vishnu.dialogmusicplayer), and I hope users find it handy to have a simple, minimal, and hassle-free dialog music player! :)

Credit where it's due: thanks to all the community members and contributors, especially Shuvashish (for all the support, backing, and suggestions), Andreas (for unrelenting support & suggestions), Jazil & Ayush (for the gorgeous design), Anand, Aswin, Akash, and Shreya (for testing & feedback). You can find the community [here](https://t.me/QuotesStatusCreator) on Telegram :)

Did you find this interesting to read? Share this with someone! Anything to add? Ping me! Or, if you're surfing around here too, let's get connected; I love talking to new people. :) You can find me on [GitHub](https://github.com/VishnuSanal), [Twitter](https://twitter.com/VishnuSanalT), and [LinkedIn](https://www.linkedin.com/in/vishnu-sanal-t/).