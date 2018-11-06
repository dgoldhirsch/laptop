# Basic Terminal Set-Up

## XCode

There are recommendations by which one can install just the command-line tools, supposedly, but none of them worked for me.  I just went to the App store and downloaded it.  I had to provide my Apple ID to do this.

## Homebrew

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
(I had to provide my system password, so that this could do various sudo things)

## Oh, My Zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

The raw zsh seems to come preinstalled with Mojave.  Had to enter my system password, during this.

## Optional: Nicer zsh theme for Term app

Replace ZSH_THEME="robbyrussel" with ="mrtazz"

## Optional: Install the IR_Black_OSX terminal theme

In github, clone-or-download this repo: https://github.com/justincase/IR_Black-OSX, choosing "Download ZIP".  Open a terminal window, select Preferences, and Import the theme.

## Optional: iTerm (to be used instead of the Term app)

There's a download-link at www.iterm2.com/version3.html.  The zipfile contains only iTerm.app, which can be moved to Applications.

iTerm.app

## Install a later version of git

MacOS comes with /bin/git. As I write this, it is git 2.17.  The latest version of git is 2.19, and, to get it I had to do two things:

First, get it.  I used brew:

```bash
brew install git
```

Now--because this is the first thing I've installed with homebrew, I had to add /usr/local/share/bin to my PATH.  I did this in .zshrc:

```bash
export PATH=/Users/myhomedir/bin:/usr/local/share/bin:$PATH
```

The first component--myhomedir/bin--has nothing to do with git or homebr:ew. Sooner or
later, I will want to execute my own executables, and, the most convenient way to do that is to have a ./bin subdirectory of ~.  So, I'm taking this opportunity to add it to PATH ahead of everything else.

## Ruby version manager

Originally, I used rvm.  For the past four+ years, I used rbenv with ruby-build.
Now, I'm switching to chruby with ruby-install:

```bash
brew install chruby
brew install ruby-install
```

## Install Ruby

```bash
ruby-install --latest ruby # brought in 2.5.3, at the time of this writing
```

Then--after restarting the terminal session (important):

```bash
chruby 2.5.3
```
* Install bundler within the /Library/Ruby/Gem

```bash
sudo gem install bundler
```
* Install postgres

```bash
brew install postgresql
brew services start postgresql
```
