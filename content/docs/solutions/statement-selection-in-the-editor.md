---
title: "Statement Selection in the Editor"
description: "How I finally got a Hugo-specific editor experience"
lead:  "How I finally got a Hugo-specific editor experience"
date: 2021-06-17T13:26:54+01:00
lastmod: 2021-06-17T13:26:54+01:00
draft: false
images: []
menu:
  docs:
    parent: "solutions"
weight: 630
toc: true
---

Out of the gate, one thing I truly didn't like about working with Hugo was that  when I encountered an `{{end}}` tag, my editor (WebStorm) didn't have a default keyboard command to find the beginning. I tried a number of approaches before (happily!) finding a solution.

1. First I tried my usual keyboard selection of a full hugo statement in my WebStorm editor. (One thing I love about Webstorm is that when I type Alt-UpArrow on the keyboard it finds increasingly large blocks. For instance: For every `</div>` end tag, I'm a keystroke away from its beginning (and visa-versa). WebStorm calls this feature "Extend Selection" because you can continue to find parents of each hierarchical level. Unfortunately, by default this oh-so-helpful keystroke doesn't work on Hugo functions.

2. I installed the Hugo Integration plugin. This seems more geared toward running the hugo server and generating new hugo file and directory structures.

3. I installed the Go Template plugin. At first this didn't seem to do anything, so I tried other methods. But this ultimately was the solution. (See below.)
4. My next "solution" was to study... to learn which functions match to an end tag. So far my list includes:
- if
- range
- with

Knowing that, I can better visually scan templates and ignore all of the other variables and functions. I landed on this solution for a while, but I still was seeking an easier way.

5. I also tried downloading GoLang to see if this would work. As with the Go Template plugin, I didn't see a difference.

6. THE SOLUTION: I circled back to the Go Template WebStorm plugin. There was a clue on the plugin description page, but it still took some experimentation. I'm on a Mac, and I had success by visiting:
   WebStorm > Preferences > Editor > Filetypes > Go template files

I added adding: `*.html` to the File name pattern list.

This was a little anxiety-provoking, because it only allows that pattern on one filetype. I knew I could return that pattern back to the HTML filetype if necessary, so I went ahead and clicked on "Reassign Wildcard."

This was the magic! Now I can have my cursor on an {{end}} tag, and WebStorm rapidly finds the beginning. As with other uses of the Alt-UpArrow, I can continue to expand the selection to other divs or statements, whatever is next in the hierarchy.

So now when I see:
``` gotemplate
        <div class="widget mb-5 tags">
            <h4 class="mb-4 widget-title">Tags</h4>
            <ul class="list-inline">
                {{- if isset .Site.Taxonomies "tags" }}
                {{- if not (eq (len .Site.Taxonomies.tags) 0) }}
                {{- range $name, $items := .Site.Taxonomies.tags }}
                <li class="list-inline-item"><a
                        href="{{ `tags/` | relLangURL }}{{ $name | urlize | lower }}">{{ $name | humanize }}</a></li>
                {{- end }}
                {{- end }}
                {{- end }}
            </ul>
        </div>
```
I can more quickly see which {{- end }} is up... literally :)

I believe I've had similar issues with other templating languages, such as Jinja and Liquid and others. I look forward to applying this technique in other circumstances.
