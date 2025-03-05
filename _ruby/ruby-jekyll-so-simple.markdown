---
title:  "Jekyll theme So-simple"
layout: single
permalink: /websetup/ruby/so-simple
author_profile: true
---

Trying to set up the so-simple jekyll theme

## Create a GitHub account

Go to [GitHub][GitHub] and create a free account.

## Fork the Jekyll theme so-simple

Go to the [Jekyll theme So-simple GitHub page][so-simple_GitHub] and Fork the So-simple repository.

so-simple_fork.png

## jekyll theme setup

You now have three options for using the Jekyll theme So-simple for your web-pages.
1. install the theme as a Ruby gem,
2. install as a remote theme, or
3. customise a Ruby gem theme.

Which alternative to use depends on, i)if you want to customise the layout and functions, and ii) if you plan to publish as (free) GitHub pages or self-hosting.

### Install theme as a Ruby gem (gem based theme)

This options is the best for self-hosting with no customisation.

#### Edit <span class='file'>Gemfile</span>

The root folder of the forked (or downloaded) theme folder contains a file named <span class='file'>Gemfile</span> (with no extension). Open that file and add the line:

```
gem "jekyll-theme-so-simple"
```

The complete content of <span class='file'>Gemfile</span> should then become:

```
source "https://rubygems.org"
gem "jekyll-theme-so-simple"
```

#### Edit <span class='file'>\_config.yml</span>

You also need to edit a second file in the root folder, <span class='file'>\_config.yml</span>. Search for the text string "_theme:_" and make sure that the line defining the theme is not commented out (i.e. do not start with a hashtag), while the line defining "_remote_theme:_" is commented out with a hashtag. The two lines should appear like this:

```
theme: jekyll-theme-so-simple
# remote_theme: mmistakes/so-simple-theme
```

#### Run <span class='terminalapp'>Bundle install</span>

With the edits above done and saved, run the [bundler][bundler] terminal command to create the Jekyll environment for you site.

<span class='terminal'>bundle install</span>

The terminal reports the progress and lists all the gems that were installed and how to find them:

```
Fetching bigdecimal 3.1.9
Fetching logger 1.6.6
Fetching json 2.10.1
Fetching jekyll-paginate 1.1.0
Fetching uri 1.0.3
Fetching rexml 3.4.1
Installing logger 1.6.6
Installing json 2.10.1 with native extensions
Installing bigdecimal 3.1.9 with native extensions
Installing jekyll-paginate 1.1.0
Installing uri 1.0.3
Installing rexml 3.4.1
Fetching net-http 0.6.0
Installing net-http 0.6.0
Fetching faraday-net_http 3.4.0
Installing faraday-net_http 3.4.0
Fetching faraday 2.12.2
Installing faraday 2.12.2
Fetching sawyer 0.9.2
Installing sawyer 0.9.2
Fetching octokit 4.25.1
Installing octokit 4.25.1
Fetching jekyll-gist 1.5.0
Installing jekyll-gist 1.5.0
Fetching jekyll-feed 0.17.0
Fetching jekyll-seo-tag 2.8.0
Fetching jekyll-sitemap 1.4.0
Installing jekyll-feed 0.17.0
Installing jekyll-seo-tag 2.8.0
Installing jekyll-sitemap 1.4.0
Fetching jekyll-theme-so-simple 3.2.0
Installing jekyll-theme-so-simple 3.2.0
Bundle complete! 1 Gemfile dependency, 48 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```

### Jekyll serve

You should now be able to use Jekyll to create a local server and view the site (theme) content in your web browser. Write the following command at the <span class='app'>Terminal</span> prompt:

<span class='terminal'>bundle exec jekyll serve</span>

If you just forked the original So-simple jekyll theme there will be quite a lot of warnings as the page comes with examples and links that are meant to be edited. But the serve command should end with something like:

```
Auto-regeneration: enabled for '/Users/thomasgumbricht/GitHub_karttur-v2/so-simple-theme'
   Server address: http://127.0.0.1:4000
 Server running... press ctrl-c to stop.
 ```

Open your browser and copy/paste the server address given above, _http://127.0.0.1:4000_, or use the local address _http://localhost:4000_. You should then see the content of your site as a web-page.

### Install theme as a remote (GitHub) theme

This options is the best for hosting your pages on GitHub.

#### Edit <span class='file'>Gemfile</span>

The root folder of the forked (or downloaded) theme folder contains a file named <span class='file'>Gemfile</span> (with no extension). Open that file and add the line:

```
gem "github-pages", group: :jekyll_plugins
```

The complete content of <span class='file'>Gemfile</span> should then become:

```
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins
```

Run the terminal command <span class='terminalapp'>bundle update</span> to verify that all required gems are installed.

<span class='terminalapp'>bundle update</span>

The information returned indicate that some of the gems are outdated and need to be replaces. Just leave that for the time being and accept the installation as it is.

#### Edit <span class='file'>\_config.yml</span>

You also need to edit a second file in the root folder, <span class='file'>\_config.yml</span>. Search for the text string "_remote_theme:_" and make sure that the line defining the theme is not commented out (i.e. do not start with a hashtag), while the line defining "_theme:_" is commented out with a hashtag. The two lines should appear like this:

```
# theme: jekyll-theme-so-simple
remote_theme: mmistakes/so-simple-theme
```

#### Run <span class='terminalapp'>Bundle install</span>

With the edits above done and saved, run the [bundler][bundler] terminal command to create the Jekyll environment for you site.

<span class='terminal'>bundle install</span>

The terminal reports the progress and lists all the gems that were installed and how to find them:

```
Bundle complete! 1 Gemfile dependency, 98 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```

### Jekyll serve

You should now be able to use Jekyll to create a local server and view the site (theme) content in your web browser. Write the following command at the <span class='app'>Terminal</span> prompt:

<span class='terminal'>bundle exec jekyll serve</span>

If you just forked the original So-simple jekyll theme there will be quite a lot of warnings as the page comes with examples and links that are meant to be edited. The first error preventing the theme to serve up:


```
Liquid Exception: Syntax Error in tag 'highlight' while parsing the following markup: Valid syntax: highlight <lang> [linenos] in CHANGELOG.md
```

I simply opened the file <span class='file'>CHANGELOG.md</span> in the root of the theme site and changed the liquid tag to simple text:

```
- Replace "highlight" tags with GitHub Flavored Markdown backticks.
```

Retrying <span class='terminalapp'>bundle exec jekyll serve</span> I get another error:

```
Liquid Exception: Liquid syntax error (line 325): 'for' tag was never closed in README-OLD.md
```

The file <span class='file'>README-OLD.md</span> contains a commented _for_ liquid on line 163 that causes the error. I change that line to:

```
{percent for post in site.categories.blog percent}
```

With these changes the jekyll theme So-simple serves up and the terminal report:

```
Generating...
Remote Theme: Using theme mmistakes/so-simple-theme
 Jekyll Feed: Generating feed for posts
              done in 5.232 seconds.
Auto-regeneration: enabled for '/Users/thomasgumbricht/GitHub_karttur-v2/so-simple-remote-theme'
Server address: http://127.0.0.1:4000
Server running... press ctrl-c to stop.
```

Open your browser and copy/paste the server address given above, _http://127.0.0.1:4000_, or use the local address _http://localhost:4000_. You should then see the content of your site as a web-page.

### Customise a Ruby gem theme

The last option is to create a customised theme by copying and editing the theme default files to your local site (repository).

Start by following the section above on [Install theme as a Ruby gem (gem based theme)][installgemtheme].

The Jekyll theme will always look for local definition files, i.e. under the root of the theme's local site. Only if a theme definition file is not available locally, Jekyll will look for the default theme gem and its content. To override the default gem you just simply copy the default gem file to the local site and edit the copy of the file in the local site.

The official Jekyll site includes a section on [Overriding theme defaultsPermalink][overridethemedefault] including how to locate the gem theme you want to apply on your local machine. For locating So-Simple theme on macOS run the terminal command

<span class='terminal'>bundle info --path jekyll-theme-so-simple</span>

```
/Users/thomasgumbricht/.gem/ruby/3.4.2/gems/jekyll-theme-so-simple-3.2.0
```



[GitHub]: https://github.com

[so-simple_GitHub]: https://github.com/mmistakes/so-simple-theme

[bundler]: https://bundler.io

[installgemtheme]: #install-theme-as-a-ruby-gem-(gem-based-theme)

[overridethemedefault]: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
