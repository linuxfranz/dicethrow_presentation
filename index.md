---
title       : Online Dice Throw Simulator
subtitle    : A Flexible Web Based Simulator For Dice Throwing
author      : F. Brummer 
job         : Senior Developer
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## When do you need dice?

There's lots of everyday situations where the need for a set of dice can arise. For example:

1. You want to play a quick game of Yahtzee.
2. The rules of your favourite role playing game ask for some special 8 or more sided dice.
3. For your statistics homework you need to roll some dice.

--- .class #id 

## What can you do about it?

### Always keep some spare dice in your pocket.
Seems reasonable at first look. But you know better. You tend to forget. Or simply change your trousers. Or - even worse - they could end up in the washing machine.

### Install a Yahtzee app on your smartphone
Yeah, nice. But what about playing a different game? 

### Install a dice throwing sim on your smartphone
Good idea! But then you always forget your smartphone. And anyway you don't want to spend any more money on the app store.

---

## Web Based Dice Simulator to the rescue!!1

* **It's always available.** You only need access to the web and voila! you got your dice simulation.
* **It's free.** No hidden in app payments and the like!
* **It's flexible.** Need 24 sided dice? Check. Need 10 of them? Check. All your dice throwing needs that could ever arise are taken care of!
* **It's fast and intuitive.** The user interface is very straight forward. It's a breeze to select the desired dice set. And throwing the dice is almost instantanious.

You can play around with the simulator at https://linuxfranz.shinyapps.io/my_product/

---

## How Does it Work?

At the heart of the Simulator there is a relatively simple R function:


```r
throw_dice <- function(sides, num_dice) {
	dice <- ""
	for (i in sample(1:sides, num_dice, replace=T)) {
		dice <- paste(dice, sprintf("[ %s ]", i))
	}
	return (dice)
}
```

Let's see this function in action by throwing 5 6-sided dice:


```r
throw_dice(6, 5)
```

```
## [1] " [ 5 ] [ 5 ] [ 4 ] [ 2 ] [ 4 ]"
```
