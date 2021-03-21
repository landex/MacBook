# Catalina Configuration 


### When you think different the steps are different?  :grin:

Hello this is my steps that I performed to configure my MacBook Pro Late 2013 with Catalina, I'm a Test Analyst and need some configuration to use my Mac. 

But I like testing some thinghs here, and I like update the software that I use to new versions. So Let's Rock!!! :guitar:

### Package Manager

#### HOMEBREW

When I buy my Mac Book Pro after some weeks the first thing that I was feeling missing was package manager. As I used Linux for a long time, I missed a package manager a lot. After some search I find the homebrew... :beer:

To installing the homebrew run command below.
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

This message will be appear.
```shell
==> This script will install:
/usr/local/bin/brew
/usr/local/share/doc/homebrew
/usr/local/share/man/man1/brew.1
/usr/local/share/zsh/site-functions/_brew
/usr/local/etc/bash_completion.d/brew
/usr/local/Homebrew
==> The following new directories will be created:
/usr/local/bin
/usr/local/etc
/usr/local/include
/usr/local/lib
/usr/local/sbin
/usr/local/share
/usr/local/var
/usr/local/opt
/usr/local/share/zsh
/usr/local/share/zsh/site-functions
/usr/local/var/homebrew
/usr/local/var/homebrew/linked
/usr/local/Cellar
/usr/local/Caskroom
/usr/local/Homebrew 
/usr/local/Frameworks
==> The Xcode Command Line Tools will be installed.

Press RETURN to continue or any other key to abort
```

Press **ENTER** and wating for few minutes.

To confirm if ***homebrew*** was installed run the command below.
```shell
yourusername@yourcomputername ~ % brew -v       
Homebrew 2.5.6
Homebrew/homebrew-core (git revision 992f9; last commit 2020-10-19)
yourusername@yourcomputername-MacBook-Pro ~ % 
```

#### CASK

Text from GitHub *"Homebrew Cask extends Homebrew and brings its elegance, simplicity, and speed to the installation and management of GUI macOS applications such as Atom and Google Chrome. We do this by providing a friendly CLI workflow for the administration of macOS applications distributed as binaries. Is the best package to install GUI apps in Mac, I liked. To install run command below."*

Installing the ***cask*** run command below:
```shell
brew install cask   
```

To confirm if the ***cask*** was installed you can run command below.
```shell
yourusername@yourcomputername ~ % cask --version
0.8.4
yourusername@yourcomputername ~ % 
```

We will testing the cask now, to install Google Chrome.  You use to search the other packages.

```shell
brew search google-chrome
```

The expected result to this search is:
```shell
yourusername@yourcomputername ~ % brew search google-chrome
==> Casks
homebrew/cask-versions/google-chrome-beta
homebrew/cask-versions/google-chrome-canary
homebrew/cask-versions/google-chrome-dev
homebrew/cask/google-chrome
yourusername@yourcomputername ~ %
```

To install Google Chrome run command below.
```shell
brew cask install google-chrome
```

Output of command indicate installation of Google Chrome.
```shell
==> Tapping homebrew/cask
Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask'...
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (8/8), done.
remote: Total 486550 (delta 3), reused 0 (delta 0), pack-reused 486542
Receiving objects: 100% (486550/486550), 222.47 MiB | 245.00 KiB/s, done.
Resolving deltas: 100% (345282/345282), done.
Updating files: 100% (3781/3781), done.
Tapped 1 command and 3688 casks (3,806 files, 238.3MB).
==> Tapping homebrew/cask-versions
Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask-versions'...
remote: Enumerating objects: 68, done.
remote: Counting objects: 100% (68/68), done.
remote: Compressing objects: 100% (56/56), done.
remote: Total 229720 (delta 36), reused 18 (delta 12), pack-reused 229652
Receiving objects: 100% (229720/229720), 59.12 MiB | 1014.00 KiB/s, done.
Resolving deltas: 100% (158117/158117), done.
Tapped 162 casks (209 files, 65.5MB).
==> Downloading https://dl.google.com/chrome/mac/stable/GGRO/googlechrome.dmg
######################################################################## 100.0%
==> Verifying SHA-256 checksum for Cask 'google-chrome'.
==> Installing Cask google-chrome
==> Moving App 'Google Chrome.app' to '/Applications/Google Chrome.app'.
🍺  google-chrome was successfully installed!
```

You can use the command ***brew list --cask*** to list the apps installed.

```shell
yourusername@yourcomputername ~ % brew list --cask
google-chrome
yourusername@yourcomputername ~ % 
```

### The Terminal :desktop_computer:

Now in Catalina the ***zshell*** is default shell of OSX. To verify if ***zshell*** is default terminal type command below.

#### ZSHELL

The Zshell for me is the best Unix shell, but I prefer manual configuration, some people like the OhMyZshell, I tried in past, but I like the feeling of old school the famous do yourself.

By default the ***Catalina*** comming with *zshell* the version that comming is ***5.7.1***, but I have impulse about the updated versions of software, I need updated to last stable version, and this sometimes generate a problem, but anyway let's go to update the current ***Zshell*** of ***Catalina***. 

Current ***zsh*** version.
```shell
yourusername@yourcomputername ~ % zsh --version
zsh 5.7.1 (x86_64-apple-darwin19.0)
yourusername@yourcomputername ~ % 
```

Now using the ***homebrew*** installing new ***ZShell*** version. Rum command below.
```shell
yourusername@yourcomputername ~ % brew install zsh  
```

Sumary output of installation.
```shell
==> Summary
🍺  /usr/local/Cellar/ncurses/6.2: 3,913 files, 8.6MB
==> Installing zsh dependency: pcre
==> Pouring pcre-8.44.catalina.bottle.tar.gz
🍺  /usr/local/Cellar/pcre/8.44: 204 files, 5.5MB
==> Installing zsh
==> Pouring zsh-5.8.catalina.bottle.tar.gz
🍺  /usr/local/Cellar/zsh/5.8: 1,531 files, 13.7MB
==> Caveats
==> ncurses
ncurses is keg-only, which means it was not symlinked into /usr/local,
because macOS already provides this software and installing another version in
parallel can cause all kinds of trouble.

If you need to have ncurses first in your PATH run:
  echo 'export PATH="/usr/local/opt/ncurses/bin:$PATH"' >> ~/.zshrc

For compilers to find ncurses you may need to set:
  export LDFLAGS="-L/usr/local/opt/ncurses/lib"
  export CPPFLAGS="-I/usr/local/opt/ncurses/include"

For pkg-config to find ncurses you may need to set:
  export PKG_CONFIG_PATH="/usr/local/opt/ncurses/lib/pkgconfig"
```

Installation done, but after continue, I'll explain some things about the **ZSHELL** I'dont know but during review of this steps I typed ***zhell*** instead of ***zshell***.

#### Zshell Files

* ***$ZDOTDIR/.zshenv:*** should not contain commands that produce output or assume the shell is attached to a tty. run command below to create empty file Run command below to create this file in your home directory.

* ***$ZDOTDIR/.zprofile:*** is sourced on all invocations of the shell, unless the -f option is set. It should contain commands to set the command search path, plus other important environment variables run command below to create empty file. Run command below to create this file in your home directory.

* ***$ZDOTDIR/.zshrc:*** is sourced in interactive shells. It should contain commands to set up aliases, functions, options, key bindings, etc.

* ***$ZDOTDIR/.zlogin:*** Same purpose than ***.zprofile***, but read just after ***.zshrc***.

* ***$ZDOTDIR/.zlogout:*** Can be used to execute commands when a shell exit.

#### Set Zshel from brew to default

To discover when ***zsh 5.8*** was installed.
```shell
yourusername@yourcomputername ~ % ls -la /usr/local/bin/zs*
lrwxr-xr-x  1 yourusername  admin  25 Oct 22 22:18 /usr/local/bin/zsh -> ../Cellar/zsh/5.8/bin/zsh
lrwxr-xr-x  1 yourusername  admin  29 Oct 22 22:18 /usr/local/bin/zsh-5.8 -> ../Cellar/zsh/5.8/bin/zsh-5.8
yourusername@yourcomputername ~ % 
```

Now that we have where the ***zsh 5.8*** was installed we will setting was default shell of **OSX Catalina**.
```shell
yourusername@yourcomputername ~ % sudo dscl . -create /Users/$USER UserShell /usr/local/bin/zsh-5.8
yourusername@yourcomputername ~ % 
```

After run command above, close terminal and open again. If window below is displayed is indicated that now the your ***OSX Catalina*** is set up with ***zsh 5.8***, for us that we will perform the manual configuration, press ***0*** to start us configuration.
```shell
This is the Z Shell configuration function for new users,
zsh-newuser-install.
You are seeing this message because you have no zsh startup files
(the files .zshenv, .zprofile, .zshrc, .zlogin in the directory
~).  This function can help you with a few settings that should
make your use of the shell easier.

You can:

(q)  Quit and do nothing.  The function will be run again next time.

(0)  Exit, creating the file ~/.zshrc containing just a comment.
     That will prevent this function being run again.

(1)  Continue to the main menu.

--- Type one of the keys in parentheses --- 
```

After press ***0*** the empty file ***.zshrc*** will be created.
```shell
yourusername@yourcomputername ~ % ls -tra .zshrc 
.zshrc
yourusername@yourcomputername ~ % 

```

To confirm that the current ***ZSHELL*** used to our system is ***5.8***.
```shell
yourusername@yourcomputername ~ % zsh --version
zsh 5.8 (x86_64-apple-darwin19.3.0)
yourusername@yourcomputername ~ % 
```

#### Starting the configuration

Create the directoy ***.zconfg*** in your home directory.
```shell
mkdir .zconfig
```

Directory created was expected.
```shell
yourusername@yourcomputername .zconfig % pwd
/Users/yourusername/.zconfig
yourusername@yourcomputername .zconfig % 
```

Add configuration in your ***.zshenv*** file, attention have four commands to run below.
```shell
yourusername@yourcomputername ~ % echo 'export XDG_CONFIG_HOME="$HOME/.zconfig"' >> .zshenv
yourusername@yourcomputername ~ % echo 'export XDG_DATA_HOME="$XDG_CONFIG_HOME/local/share"' >> .zshenv 
yourusername@yourcomputername ~ % echo 'export XDG_CACHE_HOME="$XDG_CONFIG_HOME/cache"' >> .zshenv 
```

Put your ***.zshrc*** in your ***.zconfig*** directory.
```shell
yourusername@yourcomputername ~ % mv .zshrc .zconfig/
yourusername@yourcomputername ~ % 
```

The ***ZDOTDIR*** configuration, run command below.
```shell
yourusername@yourcomputername ~ % echo 'export ZDOTDIR="$XDG_CONFIG_HOME/"' >> .zshenv
```

Other variables that we need configure in ***.zshenv***.
```shell
yourusername@yourcomputername ~ % echo 'export HISTFILE="$ZDOTDIR/.zsh_history"     # History filepath' >> .zshenv 
yourusername@yourcomputername ~ % echo 'export HISTSIZE=10000                   # Maximum events for internal history' >> .zshenv 
yourusername@yourcomputername ~ % echo 'export SAVEHIST=10000                   # Maximum events in history file' >> .zshenv 
```

The ***.zshenv*** after configuration.
```shell
yourusername@yourcomputername ~ % cat .zshenv 
export XDG_CONFIG_HOME="$HOME/.zconfig"
export XDG_DATA_HOME="$XDG_CONFIG_HOME/local/share"
export XDG_CACHE_HOME="$XDG_CONFIG_HOME/cache"

export ZDOTDIR="$XDG_CONFIG_HOME" 
export HISTFILE="$ZDOTDIR/.zsh_history" # History filepath
export HISTSIZE=10000                   # Maximum events for internal history
export SAVEHIST=10000                   # Maximum events in history file
yourusername@yourcomputername ~ %
``` 

After this close the terminal, and open again and run commands below, to confirm that the changes are ok.
```shell
yourusername@yourcomputername % echo $ZDOTDIR
/Users/yourusername/.zconfig
yourusername@yourcomputername % 
```

Configure the history file, in directory ***.zsh***. Below have commands to create a ***.zhistory*** file.
```shell
yourusername@yourcomputername ~ % cd .zconfig
yourusername@yourcomputername .zconfig % touch .zsh_history
yourusername@yourcomputername .zconfig % pwd
/Users/yourusername/.zconfig
yourusername@yourcomputername .zconfig % 
``` 

The ***.zshrc*** configuration, I prefer add aliases and other configurations in my ***.zshrc***, but fell free to configure of your way. :bowtie:

## The Next Steps :bangbang::bangbang::bangbang:

#### Syntax Highlight

Now we will download and enable the syntax highlight.

First perform the download of syntax highlight, using the git. Access the ***.zsh*** directory.
```shell
/Users/yourusername/.zconfig
```
Run command to perform download by git.
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
```
To enable the syntax Highlight. You need enable in ***.zshrc***.

```shell
landileite@landileites-MacBook-Pro .zconfig % echo '# To enable the Syntax Highlight' >> .zshrc 
echo 'source $ZDOTDIR/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh' >> $ZDOTDIR/.zshrc
```
Testing the changes of syntax highlight.



<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-04%20at%2012.35.01.png" alt="drawing" width="400"/>



#### Colored Terminal to ls commands

Not we will configure to when run some commands, the output displayed colored. I like when run *ls* command and is displayed colors, for me I use the configuration below.
```shell
echo '# LS Configuration' >> $ZDOTDIR/.zshrc
echo 'export CLICOLOR=1' >> $ZDOTDIR/.zshrc
echo 'export LSCOLORS=GxFxCxDxBxegedabagaced' >> $ZDOTDIR/.zshrc
```
To enable this you need reload the configureation file, ***source $ZDOTDIR/.zshrc*** 



<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-04%20at%2013.04.16.png" alt="drawing" width="400"/>

#### More Colors, now we will add alias to give more colors to grep command.
Attention with quotes simples and double in commands below.

```shell
echo "# Alias to Colored Grep" >> $ZDOTDIR/.zshrc
echo "alias grep='grep --color=auto'" >> $ZDOTDIR/.zshrc
echo "alias fgrep='fgrep --color=auto'" >> $ZDOTDIR/.zshrc
echo "alias egrep='egrep --color=auto'" >> $ZDOTDIR/.zshrc
```

Close and open termina again, and make test, the expected is output below.
The word Chrome was highlighted with red color.


<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-05%20at%2008.50.25.png" alt="drawing" width="500"/>




#### Fira Code

Fira code, after discover fira code and ligatures, was love at first time.:heart_eyes: :heart_eyes: :heart_eyes:
Access the github page https://github.com/tonsky/FiraCode and make download of fira code. Click in button below, and unzip the files.



<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.17.26.png" alt="drawing" width="250"/>


Unzip the filles access **ttf** folder, select all files and press right and select open with ***font book*** and make be happy.


<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.23.14.png" alt="drawing" width="350"/>

Installing the Fonts.

<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.24.01.png" alt="drawing" width="350"/>

### Set up Fira Code in terminal

Access ***Terminal*** preferences and select change the font, I prefer the ***Fira Code Retina*** see prints below to more details. :bowtie:

Click in change to change the font.


<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.38.23.png" alt="drawing" width="350"/>


Select the font, ***I prefer Fira Code Retina***


<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.38.50.png" alt="drawing" width="350"/>


Font Selected.


<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.39.00.png" alt="drawing" width="350"/>


***Testing the Fira Code Font and Ligatures in terminal*** :exclamation: :exclamation: :exclamation:



<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-06%20at%2021.40.54.png" alt="drawing" width="350"/>



#### Installing Java

The Java, the Java is the essential software to our computer, to access some app, example internet bank, icome tax software and others.

I this part we not use commands to install, we will make the download in Oracle site, and run automatic instalation... :trollface: 

No we not run automatic installation, we will make a manually installation, perform donwload of **macOS Compressed Archive** and move from your **Download** folder to **/Library/Java/JavaVirtualMachines**.
```shell
yourusername@yourcomputername Downloads % ls -ltr jdk*
-rw-r--r--@ 1 yourusername  staff  175333300 Nov  7 23:06 jdk-11.0.9_osx-x64_bin.tar.gz
yourusername@yourcomputername Downloads % pwd
/Users/yourusername/Downloads
yourusername@yourcomputername Downloads % 
```
Copying to destination folder.
```shell
sudo cp jdk-11.0.9_osx-x64_bin.tar.gz /Library/Java/JavaVirtualMachines
```

Uncompress the folder in ***JavaVirtualMachines*** folder.
```shell
yourusername@yourcomputername JavaVirtualMachines % sudo tar xzf jdk-11.0.9_osx-x64_bin.tar.gz 
Password:
yourusername@yourcomputername JavaVirtualMachines %
```

To confirm that work as expected run the two command below and compare result.
```shell
yourusername@yourcomputername ~ % java -version
java version "11.0.9" 2020-10-20 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.9+7-LTS)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.9+7-LTS, mixed mode)

yourusername@yourcomputername ~ % javac -version
javac 11.0.9
yourusername@yourcomputername ~ % 
```

## Back to Terminal configuration...

We missing two things in previos steps, first is ***PS1*** and other is ***Computer Name*** yes, the computer name. Let's Rock Again!!! :guitar:

#### The Computer Name

To changing the computer name we will use the command ***scutil***, below have commands.

* HostName
```shell
sudo scutil --set HostName osxcatalina
```

* LocalHostName
```shell
sudo scutil --set LocalHostName osxcatalina
```

* ComputerName
```shell
sudo scutil --set ComputerName osxcatalina
```

After this we will flush the DNS Cache.
```shell
dscacheutil -flushcache
```

#### The PS1

What is the PS1!? The PS1 is default interactive prompt (this is the variable most often customized).

The Values to use in PS1.

|Sequence  |Printed                                                         |
|----------|----------------------------------------------------------------|
| %T	     | System time (HH:MM).                                           |
| %*	     | System time (HH:MM:SS).                                        |
| %D	     | System date (YY-MM-DD).                                        |
| %n	     | Current username.                                              |
| %B - %b	 | Begin - end bold print.                                        |
| %U - %u	 | Begin - end underlining.                                       |
| %d	     | The current working directory.                                 |
| %~	     | The current working directory, relative to the home directory. |
| %M	     | The computer's hostname.                                       |
| %m	     | The computer's hostname (truncated before the first period).   |
| %l	     | The current tty.                                               |


Below my PS1 that I use. You need inform in your ***.kshrc***.
```shell
echo '# The PS1 Variables' >> $ZDOTDIR/.zshrc 
echo 'export PS1="[%n@%m][%~] " ' >> $ZDOTDIR/.zshrc 
```
:rainbow: **Colors and more colors**.... :rainbow:

Other thing that I like is add colors in PS1 output. 

Below have the code of colors to your increment your terminal. And to add **BOLD** and other formatting in your PS1 configuration or in output of commands in terminal.

Below have the list of colors that you can use.



<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-08%20at%2022.05.06.png" alt="drawing" width="450"/>



Example of command to define a colored output in PS1.
```shell
PS1='%B%F{108}YOURUSERNAME%f%b in %F{062}%~%f -> '
```

The output is.

<img align="center" src="https://github.com/landex/OSX/blob/master/Images/Screen%20Shot%202020-11-08%20at%2022.22.21.png" alt="drawing" width="450"/>

#### Installing New Version of Ruby
#### Installing New Version of Python
#### Installing VSCode
### Vim Configuration

So to quick edition of configuration files, or to create a simple shell script, I like use the ***VIM***.


## The References

***HomeBrew*** :link: https://brew.sh/index_pt-br

***Cask*** :link: https://github.com/Homebrew/homebrew-cask

***ZShell*** :link: https://thevaluable.dev/zsh-install-configure/

***Replace ZShell default of OSX*** :link: https://rick.cogley.info/post/use-homebrew-zsh-instead-of-the-osx-default/

***ZShell Official Manual*** :link: http://zsh.sourceforge.net/Doc/zsh_a4.pdf

***Syntax Highlighting*** :link: https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md

***Zshell Colored ls command*** :link: https://www.cyberciti.biz/faq/apple-mac-osx-terminal-color-ls-output-option/

***Zshell Colored grep command*** :link: https://www.cyberciti.biz/faq/turn-off-color-in-linux-terminal-bash-session/

***Fira Code*** :link: https://github.com/tonsky/FiraCode

***Java Download*** :link: https://www.oracle.com/java/technologies/javase-jdk11-downloads.html

***Java Helping to Install*** :link: https://stackoverflow.com/questions/52524112/how-do-i-install-java-on-mac-osx-allowing-version-switching

***Computer Name Changing*** :link: https://knowledge.autodesk.com/support/flame-products/learn-explore/caas/sfdcarticles/sfdcarticles/Setting-the-Mac-hostname-or-computer-name-from-the-terminal.html

***ZSHELL PS1 Variables*** :link: https://wiki.gentoo.org/wiki/Zsh/Guide

***ZHSELL PS1 Colors*** :link: https://medium.com/@dpeachesdev/intro-to-zsh-without-oh-my-zsh-part-1-c039de5ee22e

***ZSHELL More Customization*** :link: https://linux.die.net/man/1/zshmisc

***VIM*** :link:

***Helpful Commands*** :link: https://ss64.com/
