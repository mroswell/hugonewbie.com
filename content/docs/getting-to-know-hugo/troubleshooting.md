---
title: "The Lay of the Land"
description: "Solutions to common problems."
lead: "Solutions to common problems."
date: 2020-11-12T15:22:20+01:00
lastmod: 2020-11-12T15:22:20+01:00
draft: false
images: []
menu:
  docs:
    parent: "getting-to-know-hugo"
weight: 620
toc: true
---

So there's a lot to sort out in that [list of tags]({{< ref "all-the-things.md" >}}). I'm a longtime developer, so most of it is pretty clear in terms of its purpose. That said, for most items on the list, a little (or a lot) of research is necessary in order to better understand.

## Dots
Some things start with dots that are built into Hugo, and some are from front matter and configurations. It's not always obvious at first glance which is which.

## Current Context
- {{.}} Current context

## Equals
Three different equals.
- `eq`  This is obviously a comparison operator
- `=`  This is an assignment
- `:=` This operator seems to have a number of rules that I don't entirely understand. Whole blog posts () have been written about it.

This third operator appears in my premium in the following locations.

- {{ $categories := slice }}
- {{ $paginator := .Paginate .Data.Pages }}
- {{ $script := resources.Get "js/script.js" | minify}}
- {{ $styles := resources.Get "scss/style.scss" | toCSS | minify }}
- {{ $url := printf "%s" .Permalink | absLangURL }}
- {{ range $i, $e := .Params.tags -}}
- {{- range $name, $items := .Site.Taxonomies.categories }}
- {{- range $name, $items := .Site.Taxonomies.tags }}

The `=` shows up in one place in my premium theme:
`{{ $categories = $categories | append .Params.Category }}`

For now, I can say: these perform their functions (and it's pretty obvious what functions they perform...

(After the first item, the functions are to paginate, to add a script, to add styles, to print a url, and to iterate through a range of categories and tags. Though I'm not entirely sure of the difference between `.Params.tags` and `.Site.Taxonomies.tags`... and I don't have an idea yet of what {{ `$categories := slice` does }}
)

My main decision for now is that I don't yet have to entirely understand them to use them--like driving a car without knowing how fuel injection works. These were built into the template that I purchased and they work.)


