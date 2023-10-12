# abizern.org site in Hugo with hugo-tufte

Personal blog build with Hugo and hugo-tufte. Not so many bells and whistles, I want to try and stick to a content-centric approach.

Served from my Dreamhost account.

## Installation

Since the theme is a submodule be sure to run `git submodule update --init` as required.

## Content

All content is in the Content.org file, [ox-hugo](https://hugo-tufte.netlify.app/posts/tufte-css/) is used to turn this big ass text file into the individual Markdown files that Hugo uses to generate content.

The theme is based around [tufte-css](https://hugo-tufte.netlify.app/posts/tufte-css/).

Structured around the major subcategories of:

- Posts
- About
- Tags (this is generated)

No top level categories, just organise with tags.

## Creating Content

Create a subtree in the correct location of Content.org.

To generate a new post from the current subtree:
    C-c C-e H H (org-hugo-export-wim-to-md)
    
To regenerate the whole site:
    C-c C-e H A (org-hugo-export-wim-to-md :all-subtrees)

Posts have a Title and an optional subtitle that can be set in the front matter.

Tufte recommends two levels for content: Section (h2) and Subsection (h3), other heading styles are not supported. So don't go below two levels of nested content in a post.

### Parenthetical content

The most striking part of the Tufte style is the used of _sidenotes_ and _marginnotes_ which can be put into markdown with escaped HTML:

I have YASnippets set up for this in Markdown and there should be Org-Mode macros at the top of the `Content.org` file.

- `{{<marginnote>}} content {{</marginnote}}`
- `{{<sidenote>}} content {{</sidenote}}`

### Math

TODO: fill this out.

### Local Server

When writing code a local site can be generated with `hugo server -D`, and then navigating to the localhost url that shows in the terminal.

Math does not work locally for Safari, but it seems to do so on live websites. Testing should be done with Chrome until I figure out why Safari doesn't like the remotely fetched javascript.


## Theme

Uses the hugo-tufte theme that, added as a submodule so that I'm not a hostage to the original repository. The Github repo has a link to what it is forked from, so I can keep my submodule up to date.

## Generation and Deployment

- Clear the `content` folder to remove the generated markdown documents.
- Generate the content from `Content.org` using `C-c C-e H A`
- FTP the contents of the `public` folder to the correct place in Dreamhost

