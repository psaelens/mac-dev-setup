# Mac OS X Development setup
A guide to setting up a development environment on Mac OS X


## Homebrew

The most popular package managers for OS X ([Homebrew](http://brew.sh/)).

### Install

An important dependency before Homebrew can work is the **Command Line Tools** for **Xcode**. These include compilers that will allow you to build things from source.


	$ xcode-select --install

Finally, we can install Hombrew:

    $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

One thing we need to do is tell the system to use programs installed by Hombrew (in `/usr/local/bin`) rather than the OS default if it exists. We do this by adding `/usr/local/bin` to your `$PATH` environment variable:

    $ echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile

Open a new terminal, then run the following command to make sure everything works:

    $ brew doctor
    
### Usage

To install a package (or **Formula** in Homebrew vocabulary) simply type:

    $ brew install <formula>
        
To update Homebrew's directory of formulae, run:

    $ brew update
    
To see if any of your packages need to be updated:

    $ brew outdated
    
To update a package:

    $ brew upgrade <formula>
        
Homebrew keeps older versions of packages installed, in case you want to roll back. That rarely is necessary, so you can do some cleanup to get rid of those old versions:

    $ brew cleanup

To see what you have installed (with their version numbers):

    $ brew list --versions

## Homebrew Cask

[Homebrew Cask](http://caskroom.io) extends Homebrew and brings its elegance, simplicity, and speed to OS X applications and large binaries alike.

### Install

	$ brew install caskroom/cask/brew-cask

### Usage

Frequently used commands. More info at [How to Use Homebrew-cask](https://github.com/caskroom/homebrew-cask/blob/master/USAGE.md).

Searching for Casks

	$ brew cask search chrome

Installing Casks

	$ brew cask install google-chrome
	==> Downloading https://dl.google.com/chrome/mac/stable/GGRO/googlechrome.dmg
	==> Success! google-chrome installed to /opt/homebrew-cask/Caskroom/google-chrome/stable-channel
	==> Linking Google Chrome.app to /Users/paulh/Applications/Google Chrome.app

Uninstalling Casks

	$ brew cask uninstall google-chrome

## Terminal

[iTerm 2](http://iterm2.com) is a replacement for the Terminal app that ships with Mac OS X

### Install

    $ brew cask install iterm2

### Customize 

#### Colors 

I use the [Solarized](http://ethanschoonover.com/solarized) color scheme.

- In **iTerm2 Preferences**, under **Profiles** and **Colors**, go to **Load Presets... > Import...**, find and open the two **.itermcolors** files we downloaded.
- Go back to **Load Presets...** and select **Solarized Dark** to activate it. Voila!

### Dotfiles

    $ cd ~
    $ curl -O https://raw.githubusercontent.com/psaelens/mac-dev-setup/master/.bash_profile
    $ curl -O https://raw.githubusercontent.com/psaelens/mac-dev-setup/master/.bash_prompt
    $ curl -O https://raw.githubusercontent.com/psaelens/mac-dev-setup/master/.aliases

### Shell

ZShell (Zsh) is a shell designed for interactive use, and can be used as a powerful command interpreter for shell scripting.

    $ brew install zsh
    

add `/usr/local/bin/zsh` to /etc/shells

    $ sudo vim /etc/shells

To actually change the shell assigned to your user account run

    $ chsh -s /usr/local/bin/zsh

#### Prezto

[Prezto](https://github.com/sorin-ionescu/prezto) is the configuration framework for Zsh; it enriches the command line interface environment with sane defaults, aliases, functions, auto completion, and prompt themes.

    $ git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"

    setopt EXTENDED_GLOB
    for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
      ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
    done

## Sublime Text

### Install

Install the [Package Control](https://packagecontrol.io)

### Documentation 

* [Sublime Text 2 Documentation](https://www.sublimetext.com/docs/2/)
* [Perfect Workflow in Sublime Text](http://code.tutsplus.com/articles/perfect-workflow-in-sublime-text-free-course--net-27293)

## Intellij IDEA 

### Theme : Solarized color schemes

* [Solarized homepage]http://ethanschoonover.com/solarized
* [Solarized (Alternate)]http://www.ideacolorthemes.org/themes/83/

1. Go to `File | Import Settings...` and specify the `intellij-colors-solarized` directory.
 Clik `OK` in the dialog that appears.

2. Restart IntelliJ IDEA

3. Go to `Preferences | Editor | Colors & Fonts` and select one of the new 
color themes.

### Documentation 

* [How to be awesome in PHPStorm](https://laracasts.com/series/how-to-be-awesome-in-phpstorm)


## Related links
* https://github.com/nicolashery/mac-dev-setup
* http://code.tutsplus.com/tutorials/setting-up-a-mac-dev-machine-from-zero-to-hero-with-dotfiles--net-35449
* https://dotfiles.github.io
* 
