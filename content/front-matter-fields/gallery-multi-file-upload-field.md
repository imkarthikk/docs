---
Categories: ''
date: 2017-02-22 12:54:02 +0000
description: Allows editors to upload media and add it to a site
tags: ''
type: fields
title: Gallery/Multi-File Upload Field
image: "/docs/assets/images/Gallery%20Preview.jpg"
weight: 10
config:
  code_samples:
    yaml: |
      type: list
      name: [String]
      label: [String]
      description: [String]
      hidden: [true|false]
options_image: "/docs/assets/images/Hidden-only%20Options.jpg"
options:
- name: Hidden
  description: Hides this field in the UI, allowing for hidden default values.
  type: Toggle
how_to_use:
  hugo:
  - code: |
      <ul>
        {{ range .Params.gallery }}
          <li><img src="{{ . | relURL }}"></li>
        {{ end }}
      </ul>
  jekyll:
  - code: |
      <ul>
        {% for image in page.gallery %}
          <li><img src="{{ image | relative_url }}"></li>
        {% endfor %}
      </ul>
output:
  json: |
    {
      "gallery": [
        "/uploads/:year:/:month:/:day:/filename.ext",
        "/uploads/:year:/:month:/:day:/filename.ext"
      ]
    }
  toml: "+++ \ngallery = \"/uploads/:year:/:month:/:day:/filename.ext\"\n+++ \n"
  yaml: "--- \ngallery: /uploads/:year:/:month:/:day:/filename.ext \n--- \n"

---
The upload folder and permalink paths [can be configured](/docs/site-configuration/media-uploads/) if you don't desire the `/uploads/:year:/:month:/:day:/filename.ext` format.
