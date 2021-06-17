---
title: "All the Things"
description: "A scan for everything in my site that is surrounded by brackets"
lead: "A scan for everything in my site that is surrounded by brackets"
date: 2021-06-17T13:26:54+01:00
lastmod: 2021-06-17T13:26:54+01:00
draft: false
images: []
menu:
  docs:
    parent: "getting-to-know-hugo"
weight: 610
toc: true
---

I purchased a premium theme from https://gethugothemes.com/. I was able to adapt to it quickly. But I wanted to better understand it. I did a search for this regular expression to find all the things. (Let's see, are they called tags? Statements? Variables? Formats?).

```
\{\{.*\}\}
```
I'll make observations on all of this in upcoming posts.(For now just an observation from the second line that my theme developer doesn't check spelling. But at least the mispelling carried through on the config settings, so it actually works.)

{{< poem >}}
{{ "/tags/" | relLangURL }}{{ . | urlize }}'>{{ $e | humanize }}
{{ "&lt;!-- google analitycs --&gt;" | safeHTML }}
{{ "&lt;!-- Google Map API --&gt;" | safeHTML}}
{{ "&lt;!-- JS Plugins --&gt;" | safeHTML }}
{{ "&lt;!-- Main Script --&gt;" | safeHTML }}
{{ "&lt;!-- Main Stylesheet --&gt;" | safeHTML }}
{{ "&lt;!-- mobile responsive meta --&gt;" | safeHTML }}
{{ "&lt;!-- plugins --&gt;" | safeHTML }}
{{ "&lt;!-- preloader end --&gt;" | safeHTML }}
{{ "&lt;!-- preloader start --&gt;" | safeHTML }}
{{ "&lt;!--Favicon--&gt;" | safeHTML }}
{{ $categories := slice }}
{{ $categories = $categories | append .Params.Category }}
{{ $paginator := .Paginate .Data.Pages }}
{{ $script := resources.Get "js/script.js" | minify}}
{{ $script.Permalink }}
{{ $styles := resources.Get "scss/style.scss" | toCSS | minify }}
{{ $styles.Permalink }}
{{ $url := printf "%s" .Permalink | absLangURL }}
{{ $url }}
{{ $url }}&resubmit=true&title={{ .Title }}
{{ . | absURL }}" alt="{{ site.Title }}
{{ . | urlize }} />{{ . | humanize }}
{{ . | urlize }}/>{{ . | humanize }}
{{ . }}
{{ .bio | markdownify }}
{{ .content | markdownify }}
{{ .Content }}
{{ .Date }}
{{ .duration }}
{{ .icon }}
{{ .icon }}
{{ .image | relURL }}" alt="{{ .name }}
{{ .Inner}}
{{ .link | absURL }}
{{ .link | absURL }}" class="btn btn-white>{{ .label }}
{{ .link | safeURL }}
{{ .name | markdownify }}
{{ .name }}
{{ .Name }}
{{ .Params.Category | humanize }}
{{ .Params.Category | urlize }}
{{ .Params.Category }}
{{ .Params.Client }}
{{ .Params.Image | absURL }}
{{ .Params.Image | absURL }}" alt="{{ .Title }}
{{ .Params.Project_url | safeURL }}
{{ .Params.Year }}
{{ .percentage }}
{{ .Permalink }}
{{ .PublishDate.Format "06 jan 2006" }}
{{ .PublishDate.Format "Jan 02, 2006" }}
{{ .PublishDate.Format "January 02, 2006" }}
{{ .signature | relURL }}" alt="{{ .name }}
{{ .Site.BaseURL }}
{{ .Site.Params.address }}
{{ .Site.Params.contact_form_action }}
{{ .Site.Params.copyright | markdownify }}
{{ .Site.Params.email }}
{{ .Site.Params.gmap.gmap_api | absURL }}
{{ .Site.Params.gmap.map_latitude }}
{{ .Site.Params.gmap.map_longitude }}
{{ .Site.Params.gmap.map_marker | relURL }}
{{ .Site.Params.mobile }}
{{ .Site.Params.preloader.preloader | relURL }}
{{ .title | markdownify }}
{{ .Title }}
{{ .Title }}&body={{ $url }}
{{ .Title }}&url={{ $url }}
{{ .URL | absURL }}>{{ .Name }}
{{ `categories/` | relLangURL }}{{ $name | urlize | lower }}>{{ $name | title | humanize }}
{{ `images/favicon.png` | absURL }}
{{ `tags/` | relLangURL }}{{ $name | urlize | lower }}>{{ $name | humanize }}
{{ define "main" }}
{{ define "main"}}
{{ else }}
{{ end }}
{{ hugo.Generator }}
{{ if .button.enable }}
{{ if .HasChildren }}
{{ if .Site.Data.about.author.enable }}
{{ if .Site.Data.about.cta.enable }}
{{ if .Site.Data.about.education.enable }}
{{ if .Site.Data.about.experience.enable }}
{{ if .Site.Data.about.skill.enable }}
{{ if .Site.Data.homepage.bio.enable }}
{{ if .Site.Data.homepage.project.enable }}
{{ if .Site.Data.homepage.service.enable }}
{{ if .Site.DisqusShortname }}
{{ if .Site.Params.gmap.enable }}
{{ if .Site.Params.preloader.enable }}
{{ if and ( ne .Params.Project_url "" ) ( ne .Params.Project_url "#" ) }}
{{ if ne .Site.Params.preloader.preloader "" }}
{{ len $items}}
{{ partial "blog-sidebar.html" . }}
{{ range $i, $e := .Params.tags -}}
{{ range $paginator.Pages }}
{{ range ( $categories | uniq ) }}
{{ range (where .Site.RegularPages "Type" "music")}}
{{ range (where .Site.RegularPages "Type" "project") }}
{{ range (where .Site.RegularPages "Type" "project")}}
{{ range (where .Site.RegularPages "Type" "projects")}}
{{ range .Children }}
{{ range .Data.Pages }}
{{ range .education_item }}
{{ range .experience_item }}
{{ range .favourite_topic }}
{{ range .Params.Tags }}
{{ range .service_item }}
{{ range .Site.Menus.main }}
{{ range .Site.Params.plugins.css }}
{{ range .Site.Params.plugins.js}}
{{ range .Site.Params.social }}
{{ range .skillbar }}
{{ range first 3 ( where .Site.Pages "Type" "post" )}}
{{ replace .Inner "\n" "<br/>" | safeHtml }}
{{ replace .Inner "\n" "<br/>" | safeHTML }}
{{ replace .Name "-" " " | title }}
{{ site.Params.banner.bg_image | absURL }}
{{ site.Params.bio.bg_image | absURL }}
{{ template "_internal/disqus.html" }}
{{ template "_internal/pagination.html" . }}
{{ with .button }}
{{ with .Description }}{{ . }}{{ else }}{{ with .Site.Params.description }}{{ . }}{{ end }}{{ end }}
{{ with .Site.Data.about.author }}
{{ with .Site.Data.about.cta }}
{{ with .Site.Data.about.education }}
{{ with .Site.Data.about.experience }}
{{ with .Site.Data.about.skill }}
{{ with .Site.Data.homepage.bio }}
{{ with .Site.Data.homepage.service }}
{{ with .Site.LanguageCode }}{{ . }}{{ else }}en-US{{ end }}
{{ with .Site.Params.author }}<meta name="author" content="{{ . }}">{{ end }}
{{ with .Site.Params.google_analitycs_id}}
{{ with site.Params.bio.image }}
{{- block "main" . }}{{- end }}
{{- end -}}
{{- end }}
{{- if $i -}}, {{ end -}}
{{- if isset .Site.Taxonomies "categories" }}
{{- if isset .Site.Taxonomies "tags" }}
{{- if not (eq (len .Site.Taxonomies.categories) 0) }}
{{- if not (eq (len .Site.Taxonomies.tags) 0) }}
{{- partial "footer.html" . -}}
{{- partial "head.html" . -}}
{{- partial "header.html" . -}}
{{- partial "preloader.html" . -}}
{{- range $name, $items := .Site.Taxonomies.categories }}
{{- range $name, $items := .Site.Taxonomies.tags }}
{{< /poem >}}
