---
title:  "Gem updates"
layout: single
permalink: /websetup/ruby/ruby-update
author_profile: true
---

Regardless if you used a Ruby version manager or a bare-bone installation (see [previous][previous] post), you should check keep your Ruby environment and its gems updated when you start a new project.

The way to update gems varies dependent on how your Ruby installation route. You can also install or upgrade gems individually, or apply a gem manager to update all gems in one go.

## Individual gem updates

The default command for updating a Ruby gem is to run the terminal command <span class='terminalapp'>gem install \<gem\></span>. This command, however, is meant for the system default Ruby installation and does not affect any [Homebrew][homebrew] installation. For Homebrew installed Ruby, you could instead use [brew-gem][brew-gem]. Install brew-gem using Homebrew:

```
brew install brew-gem
```

Then use the terminal to install <span class='terminalapp'>brew-gem install \<gem\> --homebrew-ruby</span> or upgrade <span class='terminalapp'>brew-gem upgrade \<gem\> --homebrew-ruby</span> gems. For more information see the page [Managing Ruby Gems using Homebrew][brew-gem_blog].

## Update using gem manager

This section was largely taken from the post [Update Gems](https://mac.install.guide/ruby/7) by Daniel Kehoe.

Check if your system comes with a gem manager by issuing the terminal command:

```
gem -v
```

If your command returns a version number, go ahead and update <span class='terminalapp'>gem</span>

```
gem update --system
```

Use the gem manager to list your gems:

```
gem list

*** LOCAL GEMS ***

...
```
If you later want to make sure that your gems were updates, save the listed gems.

To check which gems are outdated:
```
gem outdated
...
```
You can also save this list for later if you want to control the result of the updating.

I had some outdated gems, and updated all of them in one go:

```
gem update
Updating installed gems
...
```

If you saved the list of gems prior to the update, you can now rerun the <span class='terminal'>gem list</span> command and check out that the outdated gems were updated.

## Update Jekyll theme

After updating your gems, open a <span class='app'>Terminal</span> window and change directory to your Jekyll theme site. Update the jekyll installations by running:

<span class='terminal'>bundle install</span>

```
bundle install
Using google-protobuf 4.28.3 (arm64-darwin) (was 4.28.2)
Using sass-embedded 1.81.0 (arm64-darwin) (was 1.79.3)
Bundle complete! 6 Gemfile dependencies, 46 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```

and then start the local server for your jekyll site:

<span class='terminal'>bundle exec jekyll serve</span>


Any mis-matches between your jekyll theme and the gems are reported in the terminal window.

To fix the mis-matches you need to locate your theme's gem definition. In the terminal window execute the command:

<span class='terminal'>bundle info \<jekyll-theme\></span>

```
bundle info minimal-mistakes
  * minimal-mistakes-jekyll (4.26.2)
	Summary: A flexible two-column Jekyll theme.
	Homepage: https://github.com/mmistakes/minimal-mistakes
	Path: /opt/homebrew/lib/ruby/gems/3.3.0/gems/minimal-mistakes-jekyll-4.26.2
```

To correct mis-matches and errors I opened my theme's definition in my usual editor and then searched all reported errors and corrected them manually. This procedure depends on both the Jekyll theme and the version that your are using.

## Resources

[Managing Ruby Gems using Homebrew](https://brettterpstra.com/2022/10/03/managing-ruby-gems-using-homebrew)

[previous]: ./ruby-installation

[homebrew]: https://brew.sh

[brew-gem]: https://github.com/sportngin/brew-gem

[brew-gem_blog]: https://brettterpstra.com/2022/10/03/managing-ruby-gems-using-homebrew
