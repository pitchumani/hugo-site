---
title: Hugo for personal website
authors:
  - Pitchumani
date: "2024-03-16T12:20:16+05:30"
tags:
  - hugo
  - github pages
---

Hugo's [quick-start](https://gohugo.io/getting-started/quick-start/)
is good start. But I would recommend to go through few hugo [themes](https://themes.gohugo.io/)
and their installation instructions.

I found below YouTube video to be very useful.
{{< youtube hjD9jTi_DQ4 >}}

**Things to note while using Hugo:**
- Check the Hugo version, normal or extended while selecting the theme
- Default config file is hugo.yaml/yml or hugo.toml or hugo.json. We can change
the config file while building website by passing option --config.
```
hugo server --config config-papermod.yaml
```
- If you copy or refer configuration file, check the format (yaml/ toml).
- To host the built web in github.io, the repository created shall be pushed as
yourname.github.io.git.
- Do not add 'public' directory while committing the changes. It is generated
directory, not required to be in the repo.
- When we clone the repo in different machine, make all submodules are cloned
properly (if the theme is added as submodule when you initialized the site)
```
git submodule update --init --recursive
```

**Things to note while publishing using github pages**
- The github workflow action (.github/workflows/hugo.yml) will be added by
default
- The github workflow action configuration file may require changes if the
hugo configuration file is not the default one (hugo.yaml/hugo.toml).
```
        run: |
          hugo \
            --config config-papermod.yml \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"
```
