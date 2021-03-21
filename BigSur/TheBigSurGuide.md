## The Big Sur Guide :smiley:

### The first steps is create the bootable disk. :floppy_disk:

Open your terminal and type the command below:

```shell
 sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/32BITS -- /Applications/Install\ macOS\ Big\ Sur.app/
 ```
 
 After click [ENTER] the system will request your password and confirm to erase and create bootable disk.
 
 ```shell
 Ready to start.
To continue we need to erase the volume at /Volumes/NO_NAME.
If you wish to continue type (Y) then press return: y
Erasing disk: 0%... 10%... 20%... 30%... 100%
Copying to disk: 0%...
```

To install follow details in link [Create Bootable Disk](https://www.macworld.com/article/3566910/how-to-create-a-bootable-macos-big-sur-installer-drive.html) 

### The Terminal :desktop_computer:

This is initial terminal appearance, after installed the Big Sur.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-16%20at%2007.55.18.png" alt="drawing" width="350"/>



### Configuration of appearance.

Firs, I change profile to ***Pro***, I like the transparent terminal, to access preferences, with terminal open type ***command*** + ***comma***.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-16%20at%2008.08.00.png" alt="drawing" width="350"/>



### The font.

A while ago I met a font called Fira Code, so it was love at first sight. :heart:
Make download in this link [Fira Code](https://github.com/tonsky/FiraCode). Access and click in button below to download.


<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-16%20at%2008.42.35.png" alt="drawing" width="350"/>


After make download, to install fonts, unzip the folder and copy the ***.ttf*** files to directory ***~/Library/Fonts***, see command below.

Unzip the folder

```shell
yourusername@yourcomputername-MacBook-Pro Downloads % unzip Fira_Code_v5.2.zip
```

Copy fonts, the ***.ttf*** files stay in folder ***ttf***.

```shell
yourusername@landileites-MacBook-Pro ttf % pwd
/Users/yourusername/Downloads/ttf
yourusername@yourusername-MacBook-Pro ttf % ls -ltra
total 3576
-rw-r--r--@  1 yourusername  staff  299152 Jun 12 10:02 FiraCode-Regular.ttf
-rw-r--r--@  1 yourusername  staff  285000 Jun 12 10:02 FiraCode-Light.ttf
-rw-r--r--@  1 yourusername  staff  311452 Jun 12 10:02 FiraCode-SemiBold.ttf
-rw-r--r--@  1 yourusername  staff  294960 Jun 12 10:02 FiraCode-Medium.ttf
-rw-r--r--@  1 yourusername  staff  295252 Jun 12 10:02 FiraCode-Retina.ttf
-rw-r--r--@  1 yourusername  staff  324328 Jun 12 10:02 FiraCode-Bold.ttf
drwxr-xr-x@  8 yourusername  staff     256 Jun 12 10:04 .
drwx------+ 12 yourusername  staff     384 Nov 16 08:51 ..
yourusername@yourusername-MacBook-Pro ttf % 
```

```shell
yourusername@yourusername-MacBook-Pro ttf % cp *.ttf /Library/Fonts
yourusername@yourusername-MacBook-Pro ttf % 
```

After copy close your terminal. Open again and access the preferences ***command+comma***, and set up the fira code font.


This is the original font in my case configured to my terminal.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-16%20at%2008.57.31.png" alt="drawing" width="350"/>



Setting the font.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-16%20at%2008.57.57.png" alt="drawing" width="350"/>



Testing the ligatures, I think that you will love it too!!!



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-16%20at%2008.59.08.png" alt="drawing" width="350"/>



### Install Homebrew

The great package manager is the ***HomeBrew***, run command below.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

```shell
==> This script will install:
/usr/local/bin/brew
/usr/local/share/doc/homebrew
/usr/local/share/man/man1/brew.1
/usr/local/share/zsh/site-functions/_brew
/usr/local/etc/bash_completion.d/brew
/usr/local/Homebrew
==> The following existing directories will be made group writable:
/usr/local/bin
/usr/local/etc
/usr/local/lib
==> The following existing directories will have their owner set to landileite:
/usr/local/bin
/usr/local/etc
/usr/local/lib
==> The following existing directories will have their group set to admin:
/usr/local/bin
/usr/local/etc
/usr/local/lib
==> The following new directories will be created:
/usr/local/include
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

After installation done, run command below to install cask.

Text from GitHub *"Homebrew Cask extends Homebrew and brings its elegance, simplicity, and speed to the installation and management of GUI macOS applications such as Atom and Google Chrome. We do this by providing a friendly CLI workflow for the administration of macOS applications distributed as binaries. Is the best package to install GUI apps in Mac, I liked. To install run command below."*.


### Atention
**Updating Homebrew...
Warning: You are using macOS 11.0.
We do not provide support for this released but not yet supported version.
You will encounter build failures with some formulae.
Please create pull requests instead of asking for help on Homebrew's GitHub,
Twitter or any other official channels. You are responsible for resolving
any issues you experience while you are running this
released but not yet supported version.**


```shell
yourusername@yourcomputername-MacBook-Pro ~ % brew install cask
```

The installation done, now we validate the installation was conclude run command below, to validate ***brew*** and ***cask***.

* homebrew
```shell
yourusername@yourcomputername-MacBook-Pro ~ % brew update
Already up-to-date.
yourusername@yourcomputername-MacBook-Pro ~ %
```

To complete the configuration, run command below to add configuration in yours ***.zshrc***.

```shel
[yourusername@yourcomputername][~]  echo 'export PATH="/usr/local/sbin:$PATH"' >> ~/.zconfig/.zshrc
```

To confirm that ***homebrew*** are ok in the system run command below.

```shell
[yourusername@yourcomputername][~] brew doctor   
Your system is ready to brew.
[yourusername@yourcomputername][~] 

```


* cask
```shell
yourusername@yourcomputername-MacBook-Pro ~ % brew search google-chrome
==> Casks
google-chrome                                                                           homebrew/cask-versions/google-chrome-canary
homebrew/cask-versions/google-chrome-beta                                               homebrew/cask-versions/google-chrome-dev
yourusername@yourcomputername-MacBook-Pro ~ %
```

* Installing software using ***Cask***
```shell
brew cask install google-chrome
```

After installation conclude to verify softwares installed by ***Cask*** run command below.
```shell
yourusername@yourcomputername ~ % brew list --cask
google-chrome
yourusername@yourcomputername ~ % 

```

### The ZShell

By default the OSX from Catalina version, comming with ***zhs*** Catalina with ***5.7.1*** and now the Big Sur with ***5.8***.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % zsh --version
zsh 5.8 (x86_64-apple-darwin20.0)
yourusername@yourcomputername-MacBook-Pro ~ % 
```

Understand the Zhell files:


* ***$ZDOTDIR/.zshenv:*** should not contain commands that produce output or assume the shell is attached to a tty. run command below to create empty file Run command below to create this file in your home directory.

* ***$ZDOTDIR/.zprofile:*** is sourced on all invocations of the shell, unless the -f option is set. It should contain commands to set the command search path, plus other important environment variables run command below to create empty file. Run command below to create this file in your home directory.

* ***$ZDOTDIR/.zshrc:*** is sourced in interactive shells. It should contain commands to set up aliases, functions, options, key bindings, etc.

* ***$ZDOTDIR/.zlogin:*** Same purpose than ***.zprofile***, but read just after ***.zshrc***.

* ***$ZDOTDIR/.zlogout:*** Can be used to execute commands when a shell exit.

Create in your home directory, a folder to add ***.zshrc*** to configure you ***zshell***.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % mkdir .zconfig
yourusername@yourcomputername-MacBook-Pro ~ % cd .zconfig 
yourusername@yourcomputername-MacBook-Pro .zconfig % pwd
/Users/yourusername/.zconfig
yourusername@yourcomputername-MacBook-Pro .zconfig % 
```

Add configuration in your ***.zshenv***. Attention we have four commands below to configure. You will run this command in your home directory.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export XDG_CONFIG_HOME="$HOME/.zconfig"' >> .zshenv
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export XDG_DATA_HOME="$XDG_CONFIG_HOME/local/share"' >> .zshenv 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export XDG_CACHE_HOME="$XDG_CONFIG_HOME/cache"' >> .zshenv 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export ZDOTDIR="$XDG_CONFIG_HOME"' >> .zshenv
yourusername@yourcomputername-MacBook-Pro ~ % pwd
/Users/yourusername
yourusername@yourcomputername-MacBook-Pro ~ % 
```

Create a ***.zshrc*** file in ***.zconfig*** folder.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % cd .zconfig 
yourusername@yourcomputername-MacBook-Pro .zconfig % pwd       
/Users/yourusername/.zconfig
yourusername@yourcomputername-MacBook-Pro .zconfig % touch .zshrc
yourusername@yourcomputername-MacBook-Pro .zconfig % ls -ltra
total 0
drwxr-xr-x+ 18 yourusername  staff  576 Nov 18 08:15 ..
-rw-r--r--   1 yourusername  staff    0 Nov 18 08:18 .zshrc
drwxr-xr-x   3 yourusername  staff   96 Nov 18 08:18 .
yourusername@yourcomputername-MacBook-Pro .zconfig %
```

Close and open your terminal. Testing the configuration, type command below and verify the output.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % echo $ZDOTDIR
/Users/yourusername/.zconfig/
yourusername@yourcomputername-MacBook-Pro ~ % 
```

Configure the history files.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export HISTFILE="$ZDOTDIR/.zsh_history"     # History filepath' >> .zshenv 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export HISTSIZE=10000                   # Maximum events for internal history' >> .zshenv
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export SAVEHIST=10000                   # Maximum events in history file' >> .zshenv 
```

Create the history file.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % cd $ZDOTDIR                                                                                     
yourusername@yourcomputername-MacBook-Pro .zconfig % ls -ltra
total 0
-rw-r--r--   1 yourusername  staff    0 Nov 18 08:18 .zshrc
drwxr-xr-x+ 18 yourusername  staff  576 Nov 18 08:20 ..
drwxr-xr-x   4 yourusername  staff  128 Nov 18 08:20 .
drwx------   3 yourusername  staff   96 Nov 18 08:20 .zsh_sessions
yourusername@yourcomputername-MacBook-Pro .zconfig % pwd
/Users/yourusername/.zconfig
yourusername@yourcomputername-MacBook-Pro .zconfig % touch .zsh_history
yourusername@yourcomputername-MacBook-Pro .zconfig % ls -ltra
total 0
-rw-r--r--   1 yourusername  staff    0 Nov 18 08:18 .zshrc
drwxr-xr-x+ 18 yourusername  staff  576 Nov 18 08:20 ..
drwx------   3 yourusername  staff   96 Nov 18 08:20 .zsh_sessions
-rw-r--r--   1 yourusername  staff    0 Nov 18 08:25 .zsh_history
drwxr-xr-x   5 yourusername  staff  160 Nov 18 08:25 .
yourusername@yourcomputername-MacBook-Pro .zconfig %
```

The Syntax highlight

Using the git we will install syntax highlight in your terminal.

```shell
yourusername@yourcomputername-MacBook-Pro .zconfig % pwd
/Users/yourusername/.zconfig
yourusername@yourcomputername-MacBook-Pro .zconfig % git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
Cloning into 'zsh-syntax-highlighting'...
remote: Enumerating objects: 27, done.
remote: Counting objects: 100% (27/27), done.
remote: Compressing objects: 100% (15/15), done.
remote: Total 6892 (delta 13), reused 22 (delta 12), pack-reused 6865
Receiving objects: 100% (6892/6892), 1.46 MiB | 764.00 KiB/s, done.
Resolving deltas: 100% (4657/4657), done.
yourusername@yourcomputername-MacBook-Pro .zconfig % pwd
/Users/yourusername/.zconfig
yourusername@yourcomputername-MacBook-Pro .zconfig % 
```

Set up the syntax highlight, we will configure our ***.zshrc*** file to load the syntax highlight, are two commands to run.

```shell

yourusername@yourcomputername-MacBook-Pro ~ % echo '# To enable the Syntax Highlight' >> $ZDOTDIR/.zshrc 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'source $ZDOTDIR/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh' >> $ZDOTDIR/.zshrc
yourusername@yourcomputername-MacBook-Pro ~ % 
```

To testing close and open your terminal, and type a valid commands to validate.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-18%20at%2008.40.29%20.png" alt="drawing" width="350"/>



### PS1 Varables 


What is the PS1!? The PS1 is default interactive prompt (this is the variable most often customized).

The Values to use in PS1.

|Sequence  |Printed                                                         |
|----------|----------------------------------------------------------------|
| %T	      | System time (HH:MM).                                           |
| %*	      | System time (HH:MM:SS).                                        |
| %D	      | System date (YY-MM-DD).                                        |
| %n	      | Current username.                                              |
| %B - %b	 | Begin - end bold print.                                        |
| %U - %u	 | Begin - end underlining.                                       |
| %d	      | The current working directory.                                 |
| %~	      | The current working directory, relative to the home directory. |
| %M	      | The computer's hostname.                                       |
| %m	      | The computer's hostname (truncated before the first period).   |
| %l	      | The current tty.                                               |

Below my PS1 that I use. You need inform in your ***.kshrc***.
```shell
echo '# The PS1 Variables' >> $ZDOTDIR/.zshrc 
echo 'export PS1="[%n@%m][%~] " ' >> $ZDOTDIR/.zshrc 
```
:rainbow: **Colors and more colors**.... :rainbow:

Other thing that I like is add colors in PS1 output. 

Below have the code of colors to your increment your terminal. And to add **BOLD** and other formatting in your PS1 configuration or in output of commands in terminal.

Below have the list of colors that you can use.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-08%20at%2022.05.06.png" alt="drawing" width="450"/>



Example of command to define a colored output in PS1.
```shell
PS1='%B%F{108}YOURUSERNAME%f%b in %F{062}%~%f -> '
```

The output is.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-11-08%20at%2022.22.21.png" alt="drawing" width="450"/>



### The Computer Name

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

#### Installing Java 11 LTS

The Java, the Java is the essential software to our computer, to access some app, example internet bank, icome tax software and others.

I this part we not use commands to install, we will make the download in Oracle site, and run automatic instalation... :trollface: 

No we not run automatic installation, we will make a manually installation, perform [donwload](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) of **macOS Compressed Archive** and move from your **Download** folder to **/Library/Java/JavaVirtualMachines**.
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

### Text Editor

The text editor is essential in world of computer, I use two most of time, ***Visual Studio Code*** and ***VIM***, in steps below I share the configurations that I use in my MacBook Pro.

#### VSCode

For me is the best, to install make download, unzip and copy to ***Applications***, to open the Visual Studio Code by terminal run command below.

Open VSCode, and type ***Command*** + ***Shift*** + ***P*** or press ***fn*** + ***F1*** to open command pallete.

After open ***Command Pallete*** type ***Shell*** and select the option ***Shell Command : Install code in PATH***.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-05%20at%2019.21.05.png" alt="drawing" width="450"/>



After this when you type ***code*** in your terminal the ***VSCode*** will open...

##### Fira Cude in VSCode

I talked that I like the Fira Code font, so we will configure the Fira Code in the VSCode.

Open preferences, press ***Command*** + ***comma*** (*command+,*).

The preferences will be opne.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-14%20at%2013.43.45.png" alt="drawing" width="450"/>



In search settings type ***"font"***



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-14%20at%2013.44.26.png" alt="drawing" width="450"/>



Scroll down to find **font ligatures** and click in **Edit in settings.json**



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-14%20at%2013.44.34.png" alt="drawing" width="450"/>



Paste the configuration below:
```json
{
    "editor.fontFamily": "Fira Code",
    "editor.fontSize": 13,
    "editor.fontLigatures": true,
}
```



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-14%20at%2013.45.21.png" alt="drawing" width="450"/>



Testing the changes



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-14%20at%2013.45.47.png" alt="drawing" width="450"/>



#### VIM

Is the best editor, but I use only to quick edition of scrips, files and other thinks in ***Unix Like*** systems.

I like to enable syntax highlight and line number in ***VIM*** to set up, please following the commands below.

First steps is necessary create a ***.vimrc*** file in your home directory.

```shell
[yourusername@yourcomputername][~] pwd
/Users/yourusername
[yourusername@yourcomputername][~] touch .vimrc
[yourusername@yourcomputername][~] 
```
Enable the syntax highlight.

```shell
[yourusername@yourcomputername][~] echo 'syntax enable' >> .vimrc 
[yourusername@yourcomputername][~] 
```
Testing the syntax highlight.



<img align="center" src="https://github.com/landex/BigSur/blob/main/images/Screen%20Shot%202020-12-13%20at%2017.01.29.png" alt="drawing" width="450"/>



Other thing that is ok, is enable the line numbers.

```shell
[yourusername@yourcomputername][~] echo 'set number' >> .vimrc 
[yourusername@yourcomputername][~] 
```

The line numbers help during scripts debugs. :smiley:

### Ruby 2.7.2

By the default the OSX Big Sur comming with Ruby version 2.6.3.

```shell
[yourusername@yourcomputername][~] ruby -v
ruby 2.6.3p62 (2019-04-16 revision 67580) [universal.x86_64-darwin20]
[yourusername@yourcomputername][~]
```

I love to keep the system and software always up to date. :white_check_mark: :white_check_mark: :white_check_mark:
To update ***Ruby*** and manage ***Ruby*** versions, I discover in site a new software version management.

### The asdf

Installing the dependecies of ***asdf***

```shell
[yourusername@yourcomputername][~] brew install coreutils curl git
```

Now installing the ***asdf***

```shell
[yourusername@yourcomputername][~] brew install asdf   
```

Added ***asdf*** in your profile.

```shell
[yourusername@yourcomputername][~]echo -e "\n. $(brew --prefix asdf)/asdf.sh" >> ~/.zconfig/.kshrc
```

To verify the version of ***asdf*** installed.

```shell
[yourusername@yourcomputername][~] asdf version
v0.8.0
[yourusername@yourcomputername][~]
```

Now is time to show, we will install the ***Ruby 2.7.2***.

First, install the asdf plugin for Ruby:

```shell
[yourusername@yourcomputername][~] asdf plugin add ruby
initializing plugin repository...
Cloning into '/Users/landileite/.asdf/repository'...
remote: Enumerating objects: 47, done.
remote: Counting objects: 100% (47/47), done.
remote: Compressing objects: 100% (39/39), done.
remote: Total 2647 (delta 26), reused 18 (delta 8), pack-reused 2600
Receiving objects: 100% (2647/2647), 614.73 KiB | 576.00 KiB/s, done.
Resolving deltas: 100% (1261/1261), done.
[yourusername@yourcomputername][~]
```

See all the versions of Ruby that are available, the list is very big, I'll not replace the list here.

```shell
[yourusername@yourcomputername][~] asdf list all ruby
[yourusername@yourcomputername][~]
```
We will use command below, to install ***Ruby 2.7.2***:

```shell
[yourusername@yourcomputername][~] asdf install ruby 2.7.2
[yourusername@yourcomputername][~]
```

### Python 3

By default hte OSX Big Sur comming with Python3 version 3.8.2

```shell
[yourusername@yourcomputername][~] python3 -V
Python 3.8.2
[yourusername@yourcomputername][~] 
```

## References:

:link: [Create Bootable Disk](https://www.macworld.com/article/3566910/how-to-create-a-bootable-macos-big-sur-installer-drive.html)

:link: [Permission Error](https://eclecticlight.co/2020/06/25/big-surs-signed-system-volume-added-security-protection/)

:link: [Fira Code](https://github.com/tonsky/FiraCode)

:link: [Homebrew](https://brew.sh/)

:link: [Cask](https://github.com/Homebrew/homebrew-cask)

:link: [Zshell](https://thevaluable.dev/zsh-install-configure/)

:link: [Zshell Official Manual](http://zsh.sourceforge.net/Doc/zsh_a4.pdf)

:link: [Syntax Highlight](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)

:link: [PS1 Variables](https://wiki.gentoo.org/wiki/Zsh/Guide)

:link: [PS1 Colors](https://medium.com/@dpeachesdev/intro-to-zsh-without-oh-my-zsh-part-1-c039de5ee22e)

:link: [Computer Name](https://knowledge.autodesk.com/support/flame-products/learn-explore/caas/sfdcarticles/sfdcarticles/Setting-the-Mac-hostname-or-computer-name-from-the-terminal.html)

:link: [Java Download](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)

:link: [Java Helping to Install](https://stackoverflow.com/questions/52524112/how-do-i-install-java-on-mac-osx-allowing-version-switching)

:link: [Visual Studio Code](https://code.visualstudio.com/download)

:link: [Fira Code in VSCode](https://medium.com/@qjli/daily-dev-tips-96-visual-studio-code-how-to-enable-this-new-sexy-fira-code-font-89bafbfa245f)

:link: [Code in Terminal](https://stackoverflow.com/questions/30065227/run-open-vscode-from-mac-terminal#:~:text=Open%20Visual%20Studio%20Code%20and,Now%20open%20your%20terminal%20type.)

:link: [Vim Configuration](https://www.shortcutfoo.com/blog/top-50-vim-configuration-options/#:~:text=The%20%E2%80%9Cvimrc%E2%80%9D%20Vim%20resource,%24HOME%E2%80%9D%20for%20your%20system.)

:link: [asdf](https://asdf-vm.com/#/core-manage-asdf)

:link: [asdf in github](https://github.com/asdf-vm/asdf)

:link: [Guide to isntall Ruby and Rails and asdf](https://learn-rails.com/install-rails-mac/4.html)
