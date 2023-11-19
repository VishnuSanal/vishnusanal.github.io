+++
title = "Timed out on OverLeaf? Don't worry, try this!"
date = "2023-11-19T10:16:27+05:30"
author = "Vishnu Sanal T"
authorTwitter = "VishnuSanalT" #do not include @
cover = "images/overleaf_timed_out_short.png"
tags = ["", ""]
keywords = ["overleaf", "timed-out", "ppt", "beamer", "latex"]
description = "How to workaround compile time exceeded on OverLeaf"
showFullContent = false
readingTime = true
+++

## What are we up to here?

So, you finally decide to work on that document you’ve been putting off for three months, or you want to work on that PPT that is due tomorrow! You grab your tools, open all the resources in 1500 Chrome tabs, and copy pasta everything onto your OverLeaf template. All is well for the first part or so, then you get a warning, and boom, suddenly OverLeaf says it won’t compile anymore! You try compressing your images and shortening the content, only to discover that none of these work. :(

Here’s a lil hack to get you around this dilemma, hang tight! :)

Here, I am going to use the [Ritsumeikan University Theme Beamer Template](https://www.overleaf.com/latex/templates/ritsumeikan-university-theme-beamer-template/jmfcqqptxjxk) for demonstration.

Say I have 50 slides, and I can compile 35 pages before reaching the limit.

An obvious solution would be to compile the first half as a project, compile the other half as another project, and merge them both. But this raises the concern of not getting continuous page numbers, page indicators on top, etc. ;__;

What next?

## The solution!

- Create a new project with all the sections and headings, but don't add the content yet, keep the pages empty.
- Create a duplicate of this project
- Start adding content to the first project, page by page, compiling at each step.
- Say, OverLeaf starts giving TLE on the 20th page.
- Now, start adding content to the newly created project from the 21st page.
- Voilà! Now you just have to export both of these projects to PDF & merge them together! There you have a PPT with whole content & continuous page indicators!

## Additional tips

- Always compress images, graphs etc (I use [compresspng.com](https://compresspng.com/))
- Try to reduce the use of _stepwise alerts_

## Conclusion

I showed you a trick for assembling massive projects on OverLeaf without paying for the service. Shout-outs to my classmates Salu, Shidul, Akash, and Ayush for giving me ideas to write this post. If you found this useful, share it with someone struggling with OverLeaf! Any more tips to add? Ping me! Or, if you're just surfing around here, let's get connected. I love talking to new people. :) You can find me on [GitHub](https://github.com/VishnuSanal), [Twitter](https://twitter.com/VishnuSanalT), and [LinkedIn](https://www.linkedin.com/in/vishnu-sanal-t/).