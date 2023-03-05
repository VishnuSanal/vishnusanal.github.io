+++
title = "Binary to Decimal Conversion - Did You Know This?"
date = 2022-12-18T12:37:26+05:30
author = "Vishnu Sanal T"
authorTwitter = "VishnuSanalT"
cover = ""
tags = ["", ""]
keywords = ["binary", "decimal", "conversion", "hack"]
description = "An easier way to convert a binary number to decimal"
showFullContent = false
readingTime = true
+++

# Binary to Decimal Conversion - Did You Know This?

Hi!

How do you convert a binary number to a decimal?

Say, `1011001110010001`:

What I used to do looked like this:

```
1 * 2 ^ 0 +
0 * 2 ^ 1 +
0 * 2 ^ 2 +
0 * 2 ^ 3 +
1 * 2 ^ 4 +
0 * 2 ^ 5 +
0 * 2 ^ 6 +
1 * 2 ^ 7 +
1 * 2 ^ 8 +
1 * 2 ^ 9 +
0 * 2 ^ 10 +
0 * 2 ^ 11 +
1 * 2 ^ 12 +
1 * 2 ^ 13 +
0 * 2 ^ 14 +
1 * 2 ^ 15
```

Mostly it ends in me making some mistakes & I find myself starting over!

Well, now I'll show you how to do it quickly.

Before that, let me remind you about the shift operations we all have studied in our classes. What happens when we perform a logical right shift?

```
    [0 0 0 0 1 0 1 0] # decimal: 10
      / / / / / / /
    [0 0 0 1 0 1 0] <- [0]

result: [0 0 0 1 0 1 0 0] # decimal: 20
```

So, a logical left shift results in the number getting doubled. i. e, when the digit `0` is concatenated to the end of a binary sequence, its decimal equivalent essentially gets doubled.

PS: stop here & guess what happens when the digit `1` is concatenated to the right end of a binary sequence! :)

```
    [0 0 0 0 1 0 1 0] # decimal: 10
      / / / / / / /
    [0 0 0 1 0 1 0] <- [1]

result: [0 0 0 1 0 1 0 1] # decimal: 21 (i. e, 20 + 1)
```

## So, we learnt, a binary sequence `x` when concatenated with:

```
    0: would result in 2x
    1: would result in 2x + 1
```

Now, let us get into action!!

We were converting `1011001110010001` to decimal:

`1011001110010001`

Starting with the first `1` and traversing from left to right, we get:

```                
                encountered: 1 => 1
                encountered: 0 => 2            # 2x (2 * 1)
                encountered: 1 => 5            # 2x + 1 (2 * 2 + 1)
                encountered: 1 => 11           # 2x + 1 (2 * 5 + 1)
                encountered: 0 => 22           # 2x (2 * 11)
                encountered: 0 => 44           # 2x (2 * 22)
                encountered: 1 => 89           # 2x + 1 (2 * 44 + 1)
                encountered: 1 => 179          # 2x + 1 (2 * 89 + 1)
                encountered: 1 => 359          # 2x + 1 (2 * 179 + 1)
                encountered: 0 => 718          # 2x (2 * 359)
                encountered: 0 => 1436         # 2x (2 * 718)
                encountered: 1 => 2873         # 2x + 1 (2 * 1436 + 1)
                encountered: 0 => 5746         # 2x (2 * 2873)
                encountered: 0 => 11492        # 2x (2 * 5746)
                encountered: 0 => 22984        # 2x (2 * 11492)
                encountered: 1 => 45969        # 2x + 1 (2 * 22984 + 1)
```

Well, see how easy it is! You can use the following binary numbers to practice:

  - 10101000
  - 1100100110
  - 010101001101

A massive shout-out to Prof. Soni for sharing this little hack with us! If you found this useful, share it with some computer science enthusiasts or flex this trick in your next class! Or if you're just surfing around here, drop me a message - I love talking to new people :) You can find me [here](https://github.com/VishnuSanal), [here](https://twitter.com/VishnuSanalT) & [here](https://www.linkedin.com/in/vishnu-sanal-t/).