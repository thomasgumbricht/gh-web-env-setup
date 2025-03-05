---
title:  "Ruby versions"
layout: single
permalink: /websetup/ruby/ruby-versions
author_profile: true
---

As [Jekyll][jekyll] is written in [Ruby][ruby], a Ruby environment is required for setting up Jekyll. Setting up Ruby is not difficult at first, but becomes cumbersome when you enter into version and security issues.

## Check pre-installed version

MacOS comes with a pre-installed version of Ruby. You can check the version installed by open a <span class='app'>terminal</span> window and write the command <span class='terminalapp'>ruby -v</span>. Hit return to execute the command.

If you are not sure if you have already installed Ruby, execute the terminal command <span class='terminalapp'>which -a ruby</span>. On my machine I have already installed another version of Ruby, and get this result:

```
(base) thomasgumbricht@MacBook-Air-3 ~ % which -a ruby
/opt/homebrew/opt/ruby/bin/ruby
/usr/bin/ruby
```
{: .no-copy}

The last line, _/usr/bin/ruby_, is the MacOS default Ruby installation. on my MacOS with Sonoma 14.7, the version of the default Ruby installation is 2.6. At time of writing this, November 2024, the latest Ruby version is 3.3.6. To run the latest version of Jekyll, and themes that build on later versions, you need to install a separate version of Ruby. Installing, and updating, your Ruby framework is also important for security reasons. The next document in this collection explains how to install Ruby using the MacOS installation manager [Homebrew][homebrew].

## Resources

[Ruby][ruby]

[Jekyll][jekyll]

[Homebrew][homebrew]

[ruby]: https://www.ruby-lang.org/en/

[jekyll]: https://jekyllrb.com

[homebrew]: https://brew.sh
