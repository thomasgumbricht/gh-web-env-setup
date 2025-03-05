---
layout: single
author_profile: true
permalink: /websetup/github/gh-pages
title: "Publishing jekyll documents on GitHub"
excerpt: "."
toc: true
categories_:
 - github
tag:
  - gh-pages
---

## GitHub gh-pages


### Ruby

To install Ruby under Homebrew without a version manager:

```
brew install ruby
```

The output will tell you what to do:

```
If you need to have ruby first in your PATH, run:
  echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc

For compilers to find ruby you may need to set:
  export LDFLAGS="-L/opt/homebrew/opt/ruby/lib"
  export CPPFLAGS="-I/opt/homebrew/opt/ruby/include"

For pkg-config to find ruby you may need to set:
  export PKG_CONFIG_PATH="/opt/homebrew/opt/ruby/lib/pkgconfig"
```


Then update all gems, as described [here](https://publishing-project.rivendellweb.net/updating-software-tools-homebrew-ruby-gems-and-nvm-based-node/):

```
gem outdated
gem update --system && gem update
gem cleanup
```

Run

```
gem list
```

and you should see the updates.

### Ruby with chruby

This time I chose to use [chruby] for installing ruby. I used the instructions found [here](https://mac.install.guide/ruby/).

https://mac.install.guide/ruby/12


Uninstal: [https://mac.install.guide/ruby/9](https://mac.install.guide/ruby/9)

Another site with information is [How to Install Ruby on a Mac with chruby, rbenv, or RVM](https://www.engineyard.com/blog/how-to-install-ruby-on-a-mac-with-chruby-rbenv-or-rvm/#:~:text=Once%20Homebrew%20is%20installed%2C%20you%20can%20use%20it%20to%20install%20Ruby.&text=This%20will%20install%20the%20latest,it%20becomes%20the%20default%20Ruby%20.).

That worked fine and I got Ruby v3.3.5 installed.

### Upgrade insecure gems

After pushing data to your GitHub gh-pages repo you can get security warning. These are available under the Security tag of your repo, figure 1.

github_gh-pages_security-tab.png
Figure 1

The recommendation in the example (figure 1) is to run the command:

```
gem "rexml", ">= 3.3.9"
```

Because I have installed Ruby using chruby and Homebrew, the above command does not work. Following the instructions [Update Gems](https://mac.install.guide/ruby/7), by the same site used above for chruby setup, just update the gems with the command:

```
gem update --system
gem update
```

To check the results of the update, list the gems:

```
gem list
```

To list outdated gems:

To overcome this, I first need to install [<span class='terminalapp'>brew-gem</span>](https://formulae.brew.sh/formula/brew-gem):

```
brew install brew-gem
```

Now you can replace the gem command above with:

```
brew gem install "rexml", ">= 3.3.9"
```

or

```
brew gem install rexml
```

or

```
brew gem upgrade rexml
```

I also had to upgrade the gem webrick.

To take effect, you must restart the terminal after the installation or upgrade.

But that did not work out, listing my intalled gems with the command:

```
gem list
```

The latest installe versions are not reflected in the list and I get the same security warnings.

## Deploying GitHub pages

Consult the [GitHub Pages documentation](https://docs.github.com/en/pages) for details on how to create website directly from a repository on GitHub.

###

### GitHub Actions workflow

[Managing Ruby Gems using Homebrew](https://brettterpstra.com/2022/10/03/managing-ruby-gems-using-homebrew/#:~:text=To%20upgrade%20to%20the%20latest,in%20a%20lot%20of%20cases.)




[mmistake-lists]: https://mmistakes.github.io/minimal-mistakes/edge%20case/edge-case-nested-and-mixed-lists/
