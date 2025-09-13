# A Developer's Journal

My journal about my software development experiences. A collection of notes, tutorials, and tips about software developement.

https://gaborkevinbarta.com/developers-journal


# Hugo version

This project is using an older version of hugo (v0.60.1). Use this in order to build the project:

On my Mac downloaded old build of hugo, added to `usr/local/bin` and use it as shown below:

```
hugo_0_60_1 version
```

## Project Structure

- `archetypes`: Templates for when new sections are created
- `content`: Markdown content of website
- `data`: Unused and unknown
- `docs`: Production build that is deployed to Github Pages
- `layout/partial`: Custom code to inject into theme
- `resources/gen`: Unused and unknown
- `static`: Custom css and images
- `themes/hugo-theme-learn`: Source code for theme

## Commmands

- `hugo server`: Run development
- `hugo server -D`: Run development with drafts
- `hugo`: Build production code into `docs` directory
- `hugo new --kind chapter chapter-name/_index.md`: Create new chapter markdown
- `hugo new chapter-name/section-name/_index.md`: Create new section markdown under a specific chapter

## Themes

### Learn

https://themes.gohugo.io/theme/hugo-theme-learn/en

https://github.com/matcornic/hugo-theme-learn


### Compose

https://themes.gohugo.io/compose/

## Hugo Shortcodes

https://gohugo.io/content-management/shortcodes/