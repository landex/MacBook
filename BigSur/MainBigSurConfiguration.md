# The Big Sur

Hello! This is procedure, to configure Big Sur, I'll share the configuration that I make in my MacBook Pro Late 2013!!!

## Fira Code

The best font ever for me.

To make download, in official GitHub page of [Fira Code](https://github.com/tonsky/FiraCode).

After download to install font, unzip the folder.

```shell
yourusername@yourcomputername-MacBook-Pro Downloads % unzip Fira_Code_v5.2.zip
```

Copy fonts, the .ttf files stay in folder ttf.

```shell
yourusername@yourcomputername-MacBook-Pro ttf % pwd
/Users/yourusername/Downloads/ttf
yourusername@yourcomputername-MacBook-Pro ttf %
```

```shell
yourusername@yourcomputername-MacBook-Pro ttf % ls -ltra
total 3576
-rw-r--r--@  1 yourusername  staff  299152 Jun 12 10:02 FiraCode-Regular.ttf
-rw-r--r--@  1 yourusername  staff  285000 Jun 12 10:02 FiraCode-Light.ttf
-rw-r--r--@  1 yourusername  staff  311452 Jun 12 10:02 FiraCode-SemiBold.ttf
-rw-r--r--@  1 yourusername  staff  294960 Jun 12 10:02 FiraCode-Medium.ttf
-rw-r--r--@  1 yourusername  staff  295252 Jun 12 10:02 FiraCode-Retina.ttf
-rw-r--r--@  1 yourusername  staff  324328 Jun 12 10:02 FiraCode-Bold.ttf
drwxr-xr-x@  8 yourusername  staff     256 Jun 12 10:04 .
drwx------+ 12 yourusername  staff     384 Nov 16 08:51 ..
yourusername@yourcomputername-MacBook-Pro ttf % 
```

Make the copy.

```shell
yourusername@yourcomputername-MacBook-Pro ttf % cp *.ttf /Library/Fonts
yourusername@yourcomputername-MacBook-Pro ttf % 
```

Now the **Fira Code** will be avaiable to use in your apps compatibles.

## Xcode Command Line Tools

The ***Xcode Command Line Tools*** is necessary to us continue with configuration of OSX Big Sur.

To install first you need access the directory.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % cd /Applications/Utilities/
yourusername@yourcomputername-MacBook-Pro Utilities % pwd
/Applications/Utilities
yourusername@yourcomputername-MacBook-Pro Utilities % 
```

Run command to install ***Xcode***.

```shell
yourusername@yourcomputername-MacBook-Pro Utilities % xcode-select --install
xcode-select: note: install requested for command line developer tools
yourusername@yourcomputername-MacBook-Pro Utilities % 
```

After run commant a pop up will open, to request to install, click in install, and accept the terms and wait the installation done.



<img align="center" src="https://github.com/landex/MacBook/blob/main/BigSur/BigSur_Images/Screen%20Shot%202021-01-01%20at%2017.04.50.png" alt="drawing" width="350"/>



## The ZShell

By default the OSX from Catalina version, comming with zhs Catalina with 5.7.1 and now the Big Sur with 5.8.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % zsh --version
zsh 5.8 (x86_64-apple-darwin20.0)
yourusername@yourcomputername-MacBook-Pro ~ % 
```

The Z-Files, understand the **zshell** configuration files.

* **$ZDOTDIR/.zshenv:** should not contain commands that produce output or assume the shell is attached to a tty. run command below to create empty file Run command below to create this file in your home directory.

* **$ZDOTDIR/.zprofile:** is sourced on all invocations of the shell, unless the -f option is set. It should contain commands to set the command search path, plus other important environment variables run command below to create empty file. Run command below to create this file in your home directory.

* **$ZDOTDIR/.zshrc:** is sourced in interactive shells. It should contain commands to set up aliases, functions, options, key bindings, etc.

* **$ZDOTDIR/.zlogin:** Same purpose than .zprofile, but read just after .zshrc.

* **$ZDOTDIR/.zlogout:** Can be used to execute commands when a shell exit.

We will use the home directory. 

```shell
yourusername@yourcomputername-MacBook-Pro ~ % pwd
/Users/yourusername
yourusername@yourcomputername-MacBook-Pro ~ % 
```
Creating the ***zshenv*** file to set up the configuration. Run commands below to create a file and insert configuration in the same.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % echo '# Insert the start set up of ZSHELL' >> .zshenv
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export XDG_CONFIG_HOME="$HOME/"' >> .zshenv
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export XDG_DATA_HOME="$XDG_CONFIG_HOME/local/share"' >> .zshenv 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export XDG_CACHE_HOME="$XDG_CONFIG_HOME/cache"' >> .zshenv 
yourusername@yourcomputername-MacBook-Pro ~ % echo 'export ZDOTDIR="$XDG_CONFIG_HOME"' >> .zshenv
yourusername@yourcomputername-MacBook-Pro ~ % 
```
To confirm that file and data set up was created run command below.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % cat .zshenv 
# Insert the start set up of ZSHELL
export XDG_CONFIG_HOME="$HOME/"
export XDG_DATA_HOME="$XDG_CONFIG_HOME/local/share"
export XDG_CACHE_HOME="$XDG_CONFIG_HOME/cache"
export ZDOTDIR="$XDG_CONFIG_HOME"
yourusername@yourcomputername-MacBook-Pro ~ % 
```

Creating the ***.zshrc*** file in your home folder.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % touch .zshrc
yourusername@yourcomputername-MacBook-Pro ~ % 
```

To testing the configuration, quit terminal and open again. And run command below.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % echo $ZDOTDIR
/Users/yourusername/
yourusername@yourcomputername-MacBook-Pro ~ % 
```

Syntax highlights, to enable the syntax highlights you need make download of file in git.

Create a hidden folder with name ***.syntax*** in your home direactory and using the git make a donwload.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % pwd
/Users/yourusername
yourusername@yourcomputername-MacBook-Pro ~ % 
yourusername@yourcomputername-MacBook-Pro ~ % mkdir .syntax
```

Access the folder, and run command below.

```shell
yourusername@yourcomputername-MacBook-Pro .syntax % pwd
/Users/yourusername/.syntax
yourusername@yourcomputername-MacBook-Pro .syntax % 
```

```shell
yourusername@yourcomputername-MacBook-Pro .syntax % git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
Cloning into 'zsh-syntax-highlighting'...
remote: Enumerating objects: 34, done.
remote: Counting objects: 100% (34/34), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 6899 (delta 14), reused 28 (delta 13), pack-reused 6865
Receiving objects: 100% (6899/6899), 1.46 MiB | 589.00 KiB/s, done.
Resolving deltas: 100% (4657/4657), done.
yourusername@yourcomputername-MacBook-Pro .syntax %
```

Now we will insert in our ***.zshrc*** file the command ***source*** to enable the syntax highlight. You need stay in ***.syntax*** folder created in previous command.

```shell
yourusername@yourcomputername-MacBook-Pro .syntax % pwd
/Users/yourusername/.syntax
yourusername@yourcomputername-MacBook-Pro .syntax % 
```

Run command to insert in ***.zshrc***.

```shell
yourusername@yourcomputername-MacBook-Pro .syntax % echo '# To enable the Syntax Highlight' >> $ZDOTDIR/.zshrc 
yourusername@yourcomputername-MacBook-Pro .syntax % echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
yourusername@yourcomputername-MacBook-Pro .syntax %
```

Rum command below in your home directory to reload terminal configurations.

```shell
yourusername@yourcomputername-MacBook-Pro ~ % source .zshrc 
yourusername@yourcomputername-MacBook-Pro ~ %
```

Testing syntax highlight.



<img align="center" src="https://github.com/landex/MacBook/blob/main/BigSur/BigSur_Images/Screen%20Shot%202020-11-18%20at%2008.40.29%20.png" alt="drawing" width="350"/>



### PS1 Variables

What is the PS1!? The PS1 is default interactive prompt (this is the variable most often customized).

The Values to use in PS1.

|Sequence   |Printed                                                         |
|-----------|----------------------------------------------------------------|
| %T	      | System time (HH:MM).                                           |
| %*	      | System time (HH:MM:SS).                                        |
| %D	      | System date (YY-MM-DD).                                        |
| %n	      | Current username.                                              |
| %B - %b	  | Begin - end bold print.                                        |
| %U - %u	  | Begin - end underlining.                                       |
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



<img align="center" src="https://github.com/landex/MacBook/blob/main/BigSur/BigSur_Images/Screen%20Shot%202020-11-08%20at%2022.05.06.png" alt="drawing" width="450"/>



Example of command to define a colored output in PS1.

```shell
PS1='%B%F{108}YOURUSERNAME%f%b in %F{062}%~%f -> '
```

The output is.



<img align="center" src="https://github.com/landex/MacBook/blob/main/BigSur/BigSur_Images/Screen%20Shot%202020-11-08%20at%2022.22.21.png" alt="drawing" width="450"/>



### The Computer Name

To changing the computer name we will use the command ***scutil***, below have commands.

* HostName

```shell
[yourusername@yourcomputername-MacBook-Pro][~] sudo scutil --set HostName osxbigsur
[yourusername@yourcomputername-MacBook-Pro][~] 
```

* LocalHostName

```shell
[yourusername@yourcomputername-MacBook-Pro][~] sudo scutil --set LocalHostName osxbigsur
[yourusername@yourcomputername-MacBook-Pro][~] 
```

* ComputerName

```shell
[yourusername@yourcomputername-MacBook-Pro][~] sudo scutil --set ComputerName osxbigsur
[yourusername@yourcomputername-MacBook-Pro][~] 
```

After this we will flush the DNS Cache.

```shell
[yourusername@yourcomputername-MacBook-Pro][~] dscacheutil -flushcache
[yourusername@yourcomputername-MacBook-Pro][~] 
```

Close and open your terminal to changes relfecting in terminal.

```shell
[yourusername@osxbigsur][~] 
```

## Installing Java 11 LTS

The Java, the Java is the essential software to our computer, to access some app, example internet bank, icome tax software and others.

I this part we not use commands to install, we will make the download in Oracle site, and run automatic instalation... :trollface: 

No we not run automatic installation, we will make a manually installation, perform [donwload](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) of **macOS Compressed Archive** and move from your **Download** folder to **/Library/Java/JavaVirtualMachines**.

Java compressed file dowloaded

```shell
[yourusername@yourcomputername][~/Downloads] ls -lt *jdk*
-rw-r--r--@ 1 yourusername  staff  175333300 Jan  1 18:01 jdk-11.0.9_osx-x64_bin.tar.gz
[yourusername@yourcomputername][~/Downloads] 
```

Copying to destination folder, that in this case is ***/Library/Java/JavaVirtualMachines***.

```shell
[yourusername@yourcomputername][~/Downloads] sudo cp jdk-11.0.9_osx-x64_bin.tar.gz /Library/Java/JavaVirtualMachines
```

Uncompress the folder in ***JavaVirtualMachines*** folder.

```shell
[yourusername@yourcomputername][/Library/Java/JavaVirtualMachines] sudo tar xzf jdk-11.0.9_osx-x64_bin.tar.gz 
[yourusername@yourcomputername][/Library/Java/JavaVirtualMachines] 
```

Remove the zipped file.

```shell
[yourusername@yourcomputername][/Library/Java/JavaVirtualMachines] sudo rm jdk-11.0.9_osx-x64_bin.tar.gz
[yourusername@yourcomputername][/Library/Java/JavaVirtualMachines]
```

To confirm that work as expected run the two command below and compare result.

```shell
[yourusername@yourcomputername][~] java -version
java version "11.0.9" 2020-10-20 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.9+7-LTS)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.9+7-LTS, mixed mode)
[yourusername@yourcomputername][~]

[yourusername@yourcomputername][~] javac -version
javac 11.0.9
[yourusername@yourcomputername][~]
```

## Vim

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



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-13%20at%2017.01.29.png" alt="drawing" width="450"/>



Other thing that is ok, is enable the line numbers.

```shell
[yourusername@yourcomputername][~] echo 'set number' >> .vimrc 
[yourusername@yourcomputername][~] 
```

The line numbers help during scripts debugs. :smiley:

## Visual Studio Code, The VSCode

For me is the best, to install make download, unzip and copy to ***Applications***, to open the Visual Studio Code by terminal run command below.

Open VSCode, and type ***Command*** + ***Shift*** + ***P*** or press ***fn*** + ***F1*** to open command pallete.

After open ***Command Pallete*** type ***Shell*** and select the option ***Shell Command : Install code in PATH***.



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-05%20at%2019.21.05.png" alt="drawing" width="450"/>



After this when you type ***code*** in your terminal the ***VSCode*** will open...

##### Fira Code in VSCode

I talked that I like the Fira Code font, so we will configure the Fira Code in the VSCode.

Open preferences, press ***Command*** + ***comma*** (*command+,*).

The preferences will be opne.



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-14%20at%2013.43.45.png" alt="drawing" width="450"/>



In search settings type ***"font"***



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-14%20at%2013.44.26.png" alt="drawing" width="450"/>



Scroll down to find **font ligatures** and click in **Edit in settings.json**



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-14%20at%2013.44.34.png" alt="drawing" width="450"/>



Paste the configuration below:

```json
{
    "editor.fontFamily": "Fira Code",
    "editor.fontSize": 13,
    "editor.fontLigatures": true,
}
```



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-14%20at%2013.45.21.png" alt="drawing" width="450"/>



Testing the changes



<img align="center" src="https://github.com/landex/MacBook/blobs/main/BigSur/BigSur_Images/Screen%20Shot%202020-12-14%20at%2013.45.47.png" alt="drawing" width="450"/>



# Install Homebrew

The great package manager is the **HomeBrew**, run command below.

```shell
[yourusername@yourcomputername][~] /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

To testing if **HomeBrew** was installed with sucees, run command.

```shell
[yourusername@yourcomputername][~] brew doctor
```

The output


### References

[Bootable Disk](https://www.macworld.com/article/3566910/how-to-create-a-bootable-macos-big-sur-installer-drive.html)

[Fira Code](https://github.com/tonsky/FiraCode)

[Configuration of Zshell](https://thevaluable.dev/zsh-install-configure/)

[ZShell Official Manual](http://zsh.sourceforge.net/Doc/zsh_a4.pdf)

[ZShell syntax highlights](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)

[Xcode Tools](https://developer.apple.com/forums/thread/660641)

[PS1 Variables](https://wiki.gentoo.org/wiki/Zsh/Guide)

[PS1 Colors](https://medium.com/@dpeachesdev/intro-to-zsh-without-oh-my-zsh-part-1-c039de5ee22e)

[The Computer Name](https://knowledge.autodesk.com/support/flame-products/learn-explore/caas/sfdcarticles/sfdcarticles/Setting-the-Mac-hostname-or-computer-name-from-the-terminal.html)

[Java Download](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)

[Java Helping to Install](https://stackoverflow.com/questions/52524112/how-do-i-install-java-on-mac-osx-allowing-version-switching)

[Vim](https://www.shortcutfoo.com/blog/top-50-vim-configuration-options/#:~:text=The%20%E2%80%9Cvimrc%E2%80%9D%20Vim%20resource,%24HOME%E2%80%9D%20for%20your%20system.)

[Visual Studio Code](https://code.visualstudio.com/download)

[Fira Code in VSCode](https://medium.com/@qjli/daily-dev-tips-96-visual-studio-code-how-to-enable-this-new-sexy-fira-code-font-89bafbfa245f)

[VSCode in Terminal](https://stackoverflow.com/questions/30065227/run-open-vscode-from-mac-terminal#:~:text=Open%20Visual%20Studio%20Code%20and,Now%20open%20your%20terminal%20type.)

[HomeBrew](https://brew.sh/)
