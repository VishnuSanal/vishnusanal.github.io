---
title: "When code made me feel like a \"failure\"!"
date: 2022-09-02T09:21:00+05:30
author: Vishnu Sanal T
keywords: ["DialogMusicPlayer", "DMP", "music", "simple", "minimal"]
description: "Well, not necessarily a \"failure\", but this is a story about a mistake that caused me to question my existence. ;__;"
---

Dramatic title, huh? Originally written to answer "What was your biggest failure?" for an application, I felt like I would share it here, too. :)

In the initial release of one of my projects, [DialogMusicPlayer](https://github.com/VishnuSanal/DialogMusicPlayer) there was a need to convert the path received to a new format (`Uri` to absolute path) to play the audio file because the `MediaPlayer` class needed the path to play the file. But, due to the increasing limitations Android is enforcing on newer devices and different manufacturers & platforms returning using different formats, it was difficult to do this conversion. I assumed it was a niche thing to do. So, I looked up a solution, and after a long while of surfing, I found a code snippet from Stack Overflow that does this conversion. I used that code snippet in the project; it got released & rolled onto GitHub releases. [IzzyOnDroid](https://apt.izzysoft.de/fdroid/) and [F-Droid](https://f-droid.org/) picked up the same version when DMP published F-Droid.

Almost a month after DMP got rolled on F-Droid's main repo, I discovered that the snippet from Stack Overflow was copying the file from the user's storage onto the app's private storage (a folder on `data/data/app.package.name` where an app has unlimited read/write access to) and returning the absolute path of the new location. And the file wasn't getting cleared/replaced either. So, essentially, all the music files that were opened would be copied to this folder.

Also, on the same day, late at night, I discovered that the `MediaPlayer` class had another constructor that takes `Uri` directly (with one more parameter) & uses its stream to play the music file. :O Had I taken a little time to look up the docs or at least look into the inline documentation of the IDE, I would have seen this, and this whole problem could have been avoided. Or even if I took the effort to read the code from Stack Overflow, I would have at the very least cleared the private storage folder when the app exits.

I straight away used the new constructor and wrote [the code](https://github.com/VishnuSanal/DialogMusicPlayer/commit/8f0052d2967960d0f6c79fcbd3278db5fa040150) to check & clear the private storage folder.

That night, I felt like a failure. **I felt sorry for the storage space, memory and processing power my mistake would have cost.** What if someone tried to play a couple-hour-long audiobook that takes up half a gigabyte of storage? Then, I understood the reason for the reason for [this](https://github.com/VishnuSanal/DialogMusicPlayer/issues/17) bug report I received from a user: it was failing cuz there was not enough space on the private storage folder to copy to. I even questioned my existence. I was ready to have an apology text added to the app's README file & in the app listing. But I also felt like this is not a crime per se; for all the things apps these days do, let it be background processes or using the data of users!

But, when I told this to the community, one of the members, ([Shuvashish](https://github.com/shuvashish76)), showed up and said, "If you go by the rules, our license (`GPLv3.0+`) has that covered - no liabilities, responsibilities or warranties of any kind". This is when I felt a little better. I also consoled myself with the fact that: if the user uninstalls the app, the private storage folder gets cleared, and if the user keeps on using the app & updates the app, my new code would remove the redundant files.

I have indeed learned a lot of things from this incident. The first would be the importance of community in not only giving suggestions and feedback for the project (which is invaluable in itself) but also as an emotional support & guiding light. I also learned that I should weigh in all the possible options before choosing one—at least by looking into the inline docs or just by doing a web search—and that I should always look into what a code snippet from Stack Overflow does before using that. :D

Credit where it's due, and thanks to all the community members, especially Shuvashish, Jazil, Ayush, Anand and Aswin, for being long-term supporters of me & my projects. :)

Did you find this interesting to read? Share it with someone! Anything to add? Ping me! Or, if you're just surfing around here, let's get connected. I love talking to new people. :) You can find me on [GitHub](https://github.com/VishnuSanal), [Twitter](https://twitter.com/VishnuSanalT), and [LinkedIn](https://www.linkedin.com/in/vishnu-sanal-t/).
