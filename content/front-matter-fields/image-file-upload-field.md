---
Categories: ''
date: 2017-02-22 12:54:02 +0000
description: Allows editors to upload media and add it to a site
tags: ''
type: fields
title: Image/File Upload Field
image: "/docs/assets/images/Image-File%20Upload%20Preview.jpg"
weight: 9
config:
  code_samples:
    yaml: "type: file\nname: [String]\nlabel: [String]\ndescription: [String]\nhidden:
      [true|false]\nconfig:\n  maxSize: [Number] \n"
options_image: "/docs/assets/images/Image-File%20Upload%20Options.jpg"
options:
- name: Hidden
  description: Hides this field in the UI, allowing for hidden default values.
  type: Toggle
- name: Max File Size
  description: Limit file uploads to a maximum size in MB (megabytes)
  type: Number
how_to_use:
  hugo:
  - code: <img src="{{ .Params.banner | relURL }}">
  - code: <img src="{{ .Params.banner | absURL }}">
  jekyll:
  - code: <img src="{{ page.banner | relative_url }}">
  - code: <img src="{{ page.banner | absolute_url }}">
output:
  json: "{ \n  \"banner\": \"/uploads/:year:/:month:/:day:/filename.ext\"\n} \n"
  toml: "+++ \nbanner = \"/uploads/:year:/:month:/:day:/filename.ext\"\n+++ \n"
  yaml: "--- \nbanner: /uploads/:year:/:month:/:day:/filename.ext \n--- \n"

---
The upload folder and permalink paths [can be configured](/docs/site-configuration/media-uploads/) if you don't desire the `/uploads/:year:/:month:/:day:/filename.ext` format.
