---
title:  "Ruby installation"
layout: single
permalink: /websetup/ruby/ruby-installation
author_profile: true
---

To install and maintain a separate version of Ruby on your MacOS, you can choose from a range of approaches. I use the package manager [Howebrew](https://brew.sh). Installing Homebrew is fairly easy and explained on the home page.

Once Homebrew is installed you can go on to install Ruby. But you have to make up your mind if you want a bare-bone installation or if you prefer to use a software version manager.

## Ruby version managers

When I built the [first version of Karrtur's website](kartturv1), I used [Homebrew and Ruby Version Manager RVM](karttur_setup-blog-tools). Since then more alternatives have become available. Apart from [RVM](rvm), there are also [Asdf][asdf], [Chruby][chruby] and [Frum][frum], and more, version managers available. The ones mentioned above can all be installed via [Homebrew][homebrew].

Having tried out [RVM][rvm] and [Chruby][chruby], and run into troubles with updating individual gem packages, I found the blog on [installing Ruby on MacOS][ruby4macos] by Daniel Kehoe. I recommend using Daniel's site for your MacOS installation of Ruby.

### Install chruby

Following the recommendation by Daniel Kehoe and the [official Jekyll page][https://jekyllrb.com/docs/installation/macos/] is used chruby as my Ruby version manager. Install chruby using <span class='terminalapp'>Homebrew</span>:

<span class='terminal'>brew install chruby ruby-install</span>

The terminal window reports the progress and tells you what to do once finished. Below is a summary of the commands you should run:

```
...
Add the following to the ~/.bash_profile or ~/.zshrc file:
  source /usr/local/opt/chruby/share/chruby/chruby.sh
...
```

Newer MacOS version use <span class='terminalapp'>zsh</span> as default. To check the active shell, run the command:

<span class='terminal'>echo $SHELL</span>

If the reponse is

```
/bin/zsh
```

your machine uses zsh and the line above should be added to the file <span class='file'>~/.zshrc</span>

Close and reopen the terminal window for the command to take effect.

```
...
To enable auto-switching of Rubies specified by .ruby-version files,
add the following to ~/.bash_profile or ~/.zshrc:
  source /usr/local/opt/chruby/share/chruby/auto.sh
...
```

### Install Ruby

With <span class='terminalapp'>chruby</span> installed, install ruby with the following command:

<span class='temrinal'>ruby-install ruby 3.4.2</span>

```
Successfully installed ruby 3.4.2 into /Users/thomasgumbricht/.rubies/ruby-3.4.2
```

You then have to explicitly add the version of Ruby that you just installed to either <span class='file'>~/.bash_profile</span> or <span class='file'>~/.zshrc</span>

```
echo "chruby ruby-3.4.2" >> ~/.zshrc
```

Run the command <span class='terminal'>chruby</pass> to see that it worked:

```
 * ruby-3.4.2
```

Close and restart the <span class='app'></span> and inquire which version of Ruby that is hooked up to the terminal:

<span class='terminal'>ruby -v</span>

```
ruby 3.4.2 (2025-02-15 revision d2930f8e7a)
```

If the response you get is an older version make sure you added the required commands to <span class='file'>~/.bash_profile</span>/<span class='file'>~/.zshrc</span> and closed and restarted the terminal.

### Jekyll

With the latest version of Ruby installed you can install the gem for Jekyll:

```
gem install jekyll
```


## Resources

[Howebrew][homebrew]

[RVM][rvm]

[Asdf][asdf]

[Chruby][chruby]

[Frum][frum]

[blog on installing Ruby on MacOS][ruby4macos]

[Minimal Mistakes Jekyll Theme][mmistakes]

[homebrew]: https://brew.sh

[rvm]: https://rvm.io

[asdf]: https://asdf-vm.com

[chruby]: https://github.com/postmodern/chruby

[frum]:https://github.com/TaKO8Ki/frum

[mmistakes]: https://mmistakes.github.io/minimal-mistakes/

[kartturv1]: https://karttur.github.io

[karttur_setup-blog-tools]: https://karttur.github.io/setup-blog/2017/12/21/setup-blog-tools.html

[ruby4macos]: https://mac.install.guide/ruby/

[ruby4macos_13]: https://mac.install.guide/ruby/13
