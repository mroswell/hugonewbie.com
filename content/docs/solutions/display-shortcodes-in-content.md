---
title: "Display Shortcodes in Content"
description: "Documentation (this site, for instance) often requires the display of Hugo codes"
lead: "Documentation (this site, for instance) often requires the display of Hugo codes"
date: 2021-06-17T13:26:54+01:00
lastmod: 2021-06-17T13:26:54+01:00
draft: false
images: []
menu:
  docs:
    parent: "solutions"
weight: 620
toc: true
---
## Problem
In the [Retain Line Breaks]({{< ref "retain-line-breaks.md" >}}) page, I wanted to display the `poem` shortcode, rather than interpret it. I placed it inside three backticks, and thought that would do the trick. But instead: `hugo server` tried to interpret the shortcode and complained  that I had an `Error building site: failed to extract shortcode: template for shortcode "poem" not found.`

## Solution

I'm grateful to dkebler, who posed a similar question, and to rdwatters who offered a  solution: https://discourse.gohugo.io/t/solved-how-to-make-hugo-ignore-shortcode-delimiters-e-g-when-used-in-code-blocks/6045

I still had trouble figuring out what the end code should look like, and finally figured out that the end tag should look like this:
```
{{</** /poem **/>}}
```
(BTW, to type that I needed two asterisks, to enable it to display one.)
