---
title: "Retain Line Breaks"
description: "A scan for everything in my site that is surrounded by brackets"
lead: "A scan for everything in my site that is surrounded by brackets"
date: 2021-06-17T13:26:54+01:00
lastmod: 2021-06-17T13:26:54+01:00
draft: false
images: []
menu:
  docs:
    parent: "solutions"
weight: 610
toc: true
---
## Problem
On my http://MarjorieRoswell.com website, I wanted to add light Verse, but by default, with my premium theme, any line ends in my poems were ignored.

## Solution

I'm grateful to Bep who offered a shortcode solution: (https://discourse.gohugo.io/t/retain-line-breaks-in-plain-text-paragraph/605/4)

I created a shortcode called poem.html, which contained this:
```

{{ replace .Inner "\n" "<br/>" | safeHTML }}
```
I apply it this way. I know there are other ways of going about this, but this is what worked for me.
```
{{</* poem */>}}
Ingredients with chlorine and the quats aren’t puritanical
So better choose the thymol that is sourced from a botanical!
{{</* /poem */>}}
```

Admittedly, along the way, I got `failed to extract shortcode: template for shortcode "poem" not found`. (Seems when codes fail in Hugo they break the whole site.) I do'nt remember exactly what the shift was that made the code work, but I think I resolved by putting the shortcode in the right place, and honoring capitalization.

(Extra points if you can guess what the tune was for the lyrics I wrote above.)
