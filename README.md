# 4d-tip-github-pages
How to add 4D code highlight to GitHub Pages.

# Introduction

It's really easy to publish a public repository as a [GitHub Pages site](https://pages.github.com).

As described in the official [Quickstart](https://docs.github.com/en/pages/quickstart), you just need to 

1. Click **Settings**
2. Click Code and automation > **Pages**
3. Select **main** branch, **/ (root)** path, and save

<img src="https://github.com/miyako/4d-tip-github-pages/assets/1725068/0a7ceb19-09a9-420c-bd29-630639c1b982" height="40" />

…and that's it.

To add a [Jekyll Theme](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll) you just need to

1. add a file named `_config.yml` to the root of the repository
2. add a line to the file that specifies one of the [supported themes](https://pages.github.com/themes/), e.g.

```yml
theme: jekyll-theme-minimal
```

You can also add 4D code to the page using markdown, but here is the problem; syntax highlighting is not applies on GitHub Pages.

This is because the default syntax highlighter does not support the 4D language.

# Solution

First, goto [highlightjs/highlight.js](https://github.com/highlightjs/highlight.js) and clone the repository. This library supports the 4D language.

Next, follow the [instruction](https://highlightjs.readthedocs.io/en/latest/building-testing.html) to build `highlight.js`.

Open Terminal at the root of the repository. You can specify the languages you want to include in the build, e.g. 

```
node tools/build.js 4d css javascript xml json sql yaml php
```

