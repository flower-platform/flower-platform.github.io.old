# Introduction

This web site is statically generated using [jekyll](http://jekyllrb.com/). And, its source code is kept in this GitHub repository, and served by GitHub Pages. Anyone can contribute to this web site, by forking this repository (and then submitting a pull request).

## The Mechanics of Static Generation

The pages of the web site are written in **Markdown**. Jekyll offers a scripting engine (with loops, conditionals, etc.). When the site is generated, the Markdown syntax is parsed, and the scripts/macros are interpreted. The result is a static site (i.e. a lot of HTML files) with a lot of features, that would normally exist in a PHP style web site (e.g. include templates, count number of articles for a category, etc.).

When GitHub Pages detects a commit on the Git repo of this site, it will regenerate it, and make it available to users in a couple of minutes. That means, that for small modifications (e.g. correct typing error, etc.) one can commit directly.

However, for serious content update, a local jekyll & friends system needs to be installed, in order to be able to instantly see modifications.

# Installing Jekyll & Friends Locally

For a Win 32/64 environment, here are the steps.

* Install Ruby from [here](http://rubyinstaller.org/downloads/). Version 1.9.3 is recommended for Win, because newer versions have small issues (e.g. not all plugins available/compiled, etc.). E.g. put it here: `c:\Ruby193`
* Install Development Kit, from the same location as above. E.g. put it here: `c:\Ruby193\ruby-dev-kit`
* From the directory above, run the following commands (cf. the [DevKit tutorial](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit)):
```
ruby dk.rb init
ruby dk.rb install
```
* Install Jekyll cf. the [GitHub Pages doc](https://help.github.com/articles/using-jekyll-with-pages) / Step 2:
```
gem install bundler
```
* Cf. step 3 of the above doc: a ``Gemfile`` should already exist in the repo root (so you don't need to create it). It should point to the required dependencies/versions, as they are [installed on GitHub Pages](https://pages.github.com/versions/). Run:
```
gem install github-pages
gem install wdm
```

# Running Jekyll

In order to see the site locally, go to the repo root and type:

```
jekyll serve --watch
```

The site should now be available at [http://localhost:4000](http://localhost:4000).

A couple of userful commands (although creation by copy/paste is also possible). To add a new post 

```
rake post title="Title of post" tags=[tag1, tag2]
```
    
To add a new page:
	
```
rake page name="page_name.md"
```

# Hints on Editing (Markdown Syntax, Bootstrap, Etc.)

I recommend the following links:
* https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
* https://daringfireball.net/projects/markdown/ - The official guide, although I find it less readable than the above.
* http://kramdown.gettalong.org/syntax.html - The description of the syntax (differences and enhancements from the standard markdown) that is offered by **kramdown** (the markdown parser used by this site).
* http://getbootstrap.com/ - Reference Doc for the Bootstrap framework 

## Mixing HTML and Markdown

In order to use HTML in a Markdown file, you just put the html code. Cf. this [Kramdown doc](http://kramdown.gettalong.org/syntax.html#html-blocks), only "block level" elements behave like this (e.g. ``<div>``, ``<p>``, etc.). Other elements (i.e. "span level"; e.g. ``<button>``, ``<a>``, etc.) don't work out of the box. They should be surrounded with block level tags.

If you have Markdown text inside HTML blocks, you should add ``markdown="1"`` and you should close the block (e.g. ``<div>``) on a new line.

```html
<h1>My HTML <b>heading</b></h1>

<!-- Not OK -->
<button ...>...</button>

<!-- OK -->
<div><button ...>...</button></div>

<!-- Markdown content not rendered -->
<div class="...">
Hello **world**.
</div>

<!-- Markdown content rendered -->
<div markdown="1" class="...">
Hello **world**.
</div>

<!-- Not OK, because <div> ends on same line -->
<div markdown="1" class="...">Hello **world**.</div>
```


