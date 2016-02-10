Laptop
======
[![Build Status](https://travis-ci.org/amoose/laptop.svg)](https://travis-ci.org/amoose/laptop)

Laptop is a script to set up an OS X computer for web development.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

We support:

* [OS X Yosemite (10.10)](https://www.apple.com/osx/)
* OS X Mavericks (10.9)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Begin by opening the Terminal application on your Mac. The easiest way to open
an application in OS X is to search for it via [Spotlight]. The default
keyboard shortcut for invoking Spotlight is `command-Space`. Once Spotlight
is up, just start typing the first few letters of the app you are looking for,
and once it appears, press `return` to launch it.

In your Terminal window, copy and paste each of these two commands one at a
time, then press `return` after each one to download and execute the
script, respectively:

```sh
curl -sSL https://raw.githubusercontent.com/amoose/laptop/master/mac \
bash -s stable 2>&1 | tee ~/laptop.log
```
The [script](https://github.com/amoose/laptop/blob/master/mac) itself is
available in this repo for you to review if you want to see what it does
and how it works.

Note that the script will ask you to enter your OS X password at various
points. This is the same password that you use to log in to your Mac.
If you don't already have it installed, GitHub for Mac will launch
automatically at the end of the script so you can set up everything you'll
need to push code to GitHub.

Once the script is done, make sure to quit and relaunch Terminal.

More [detailed instructions with a video][video] are available in the Wiki.

[Spotlight]: https://support.apple.com/en-us/HT204014
[video]: https://github.com/amoose/laptop/wiki/Detailed-installation-instructions-with-video

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`. Read through it to see if
you can debug the issue yourself. If not, copy the lines where the script
failed into a [new GitHub
Issue](https://github.com/amoose/laptop/issues/new) for us. Or, attach the
whole log file as an attachment.

What it sets up
---------------

* [CloudApp] for sharing screenshots and making an animated GIF from a video
* [Cloud Foundry CLI] for command line access to 18F's Cloud Foundry-based application platform
* [Flux] for adjusting your Mac's display color so you can sleep better
* ~~[GitHub Desktop] for setting up your SSH keys automatically~~
* [Homebrew] for managing operating system libraries
* [Homebrew Cask] for quickly installing Mac apps from the command line
* [Homebrew Services] so you can easily stop, start, and restart services
* [hub] for interacting with the GitHub API
* [ImageMagick] for cropping and resizing images
* ~~[MySQL] for storing relational data~~
* [n] for managing Node.js versions if you do not have [Node.js] already installed (Includes latest [Node.js] and [NPM], for running apps and installing JavaScript packages)
* [PhantomJS] for headless website testing (unless on El Capitan, due to [this bug](https://github.com/Homebrew/homebrew/issues/42249))
* [Postgres] for storing relational data
* ~~[pyenv] for managing Python versions if you do not have [Python] already installed (includes the latest 3.x [Python])~~
* [Redis] for storing key-value data
* [RVM] for managing Ruby versions (includes [Bundler] and the latest [Ruby])
* [Slack] for communicating with your team
* [Sublime Text 3] for coding all the things
* [SizeUp] window management
* [Caffeine] for keeping the mac awake
* [The Silver Searcher] for finding things in files
* ~~[Virtualenv] for creating isolated Python environments (via [pyenv] if it is installed)~~
* ~~[Virtualenvwrapper] for extending Virtualenv (via [pyenv] if it is installed)~~
* [Zsh] as your shell

[Bundler]: http://bundler.io/
[CloudApp]: http://getcloudapp.com/
[Cloud Foundry CLI]: https://github.com/cloudfoundry/cli
[Flux]: https://justgetflux.com/
[GitHub Desktop]: https://desktop.github.com/
[Homebrew]: http://brew.sh/
[Homebrew Cask]: http://caskroom.io/
[Homebrew Services]: https://github.com/gapple/homebrew-services
[hub]: https://github.com/github/hub
[ImageMagick]: http://www.imagemagick.org/
[MySQL]: https://www.mysql.com/
[n]: https://github.com/tj/n
[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[PhantomJS]: http://phantomjs.org/
[Postgres]: http://www.postgresql.org/
[Python]: https://www.python.org/
[pyenv]: https://github.com/yyuu/pyenv/
[Redis]: http://redis.io/
[Ruby]: https://www.ruby-lang.org/en/
[RVM]: https://github.com/wayneeseguin/rvm
[Slack]: https://slack.com/
[Sublime Text 3]: http://www.sublimetext.com/3
[SizeUp]: http://www.irradiatedsoftware.com/sizeup/
[Caffeine]: https://itunes.apple.com/us/app/caffeine/id411246225?mt=12
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Virtualenv]: https://virtualenv.pypa.io/en/latest/
[Virtualenvwrapper]: http://virtualenvwrapper.readthedocs.org/en/latest/#
[Zsh]: http://www.zsh.org/

It should take less than 15 minutes to install (depends on your machine and
internet connection).

Customize in `~/.laptop.local`
------------------------------

Your `~/.laptop.local` is run at the end of the `mac` script.
Put your customizations there. This repo already contains a `.laptop.local`
you can use to get started. It lets you install the following tools
(commented out by default):

* [Atom] - GitHub's open source text editor
* [Exuberant Ctags] for indexing files for vim tab completion
* [Firefox] for testing your website on a browser other than Chrome
* [iTerm2] - an awesome replacement for the OS X Terminal
* [reattach-to-user-namespace] to allow copy and paste from Tmux
* [Tmux] for saving project state and switching between projects
* [Vim] for those who prefer the command line

[Atom]: https://atom.io/
[Exuberant Ctags]: http://ctags.sourceforge.net/
[Firefox]: https://www.mozilla.org/en-US/firefox/new/
[iTerm2]: http://iterm2.com/
[reattach-to-user-namespace]: https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard
[Tmux]: http://tmux.sourceforge.net/
[Vim]: http://www.vim.org/

For example:

```sh
#!/bin/sh

# brew_cask_install 'atom'
# brew_cask_install 'firefox'
brew_cask_install 'iterm2'

# brew_install_or_upgrade 'vim'
# brew_install_or_upgrade 'ctags'
# brew_install_or_upgrade 'tmux'
# brew_install_or_upgrade 'reattach-to-user-namespace'
```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`, `brew_install_or_upgrade`,
`gem_install_or_update`, and `brew_cask_install` can be used in your
`~/.laptop.local`.

```sh
# Go to your OS X user's root directory
cd ~

# Download the sample file to your computer
curl --remote-name https://raw.githubusercontent.com/amoose/laptop/master/.laptop.local
```

Credits
-------

The 18F laptop script is based on and inspired by
[thoughtbot's laptop](https://github.com/thoughtbot/laptop) script.

### Public domain

thoughtbot's original work remains covered under an [MIT License](https://github.com/thoughtbot/laptop/blob/c997c4fb5a986b22d6c53214d8f219600a4561ee/LICENSE).

18F's work on this project is in the worldwide [public domain](LICENSE.md), as are contributions to our project. As stated in [CONTRIBUTING](CONTRIBUTING.md):

> This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
>
> All contributions to this project will be released under the CC0 dedication. By submitting a pull request, you are agreeing to comply with this waiver of copyright interest.
