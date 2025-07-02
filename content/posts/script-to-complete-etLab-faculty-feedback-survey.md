---
title: 'Script to Complete etLab faculty feedback survey'
date: 2024-01-24T14:58:02+05:30
author: Vishnu Sanal T
keywords: ["etLab", "survey", "KTU"]
description: "Silly script that helps you with etLab surveys"
---

Hii, glad to meet a fellow KTU student! Sooo, you log into etLab to check attendance for a class you have been skipping, to check the marks of the series tests, or to submit an assignment that you painstakingly copied from someone! :)

There, you are redirected to the survey page, and you can't do anything else in etLab without completing this freakin' survey.


We all know, how everyone fills out this form; "excellent", "very good", "appreciable" etc. I use the following script & paste it into the browser console (`F12` -> `Console` tab) to mark these options for me.

```
document.querySelectorAll('ul.survey li').forEach(function (item) {
    const radios = item.querySelectorAll('input[type="radio"]');
    if (radios.length > 0) {
        radios[0].checked = true; // Check the first radio button
    }
});
```

PS1: you'd have to manually open each form, run the script & submit it. I felt too lazy to do that with code. Ofc, I can try if you can help me! :)

PS3: I really don't know what I am doing. xD Feel free to roast my poor JS! :)
