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
var radios = document.querySelectorAll('input[type=radio]')

var array = [1, 6, 11, 16, 20, 23, 27, 30, 34, 38, 42]

var arrayIndex = 0;

for (let i = 0; i < radios.length; i++) {
    const element = radios[i];

    if (array[arrayIndex] == element.value) {
        element.checked = true;

        arrayIndex++;
    }
}
```

PS1: you'd have to manually open each form, run the script & submit it. I felt too lazy to do that with code. Ofc, I can try if you can help me! :)

PS2: the variable `arrayIndex` exists only cuz `Array#includes` didn't work on my PC™

PS3: I really don't know what I am doing. xD Feel free to roast my poor JS! :)