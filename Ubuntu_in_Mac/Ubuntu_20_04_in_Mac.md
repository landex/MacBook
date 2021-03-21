# Hello! Everyone I hope you are all well !!! :smiley:

So in these MD file, I'll share with your the steps by steps that I performed to configure a Ubuntu 20.04 in Mac Book Pro Late 2013.
I know that my Mac is compatible with the new OSX **BIG SUR**. But from the **MOJAVE** I see that the performance of my Mac are depreacted, sometime the system freeze and need to hold shutdown to turn off and restart the Mac.

So because this I'll replace the OSX to Linux! Why my choise is Ubuntu!?
I used Ubuntu for the first time, in 2007 the version was *07.10 – Gutsy Gibbon*. After this I use other Linux versions, I try Mint, Mageia, Fedora, Arch, Manjaro, OpenSuse, FreeBSD and Windows.

But in 2015 I buy my MacBook, because **in Brazil is very expensive**, I hold money for 3 years to buy this Mac, so in 2015 I buy a version of 2013. 

I liked from the first time my mac, but after 5 years the hardware and software wedding is over... :broken_heart:

Now the new MacBook have a price very high out of my reality, and a good laptop is very expensive, and so to hold for more 3 year, I solve change from OSX to Linux.

Ok, ok! this previous text is enough, but I not answered why Ubuntu, because is the best linux to beginner and is the more stable to install in macbooks, I'm not beginner in Linux, but I want a stable OS in my mac.

I'll not talk about instalation stpes, due the installation software is intuitive.

### Let's go to Ubuntu 20.04

#### First Step before is update the system
In GnomeTerminal run command below.

```shell
youruser@ubuntu:~$ sudo apt update
```

Now run command below.

```shell
youruser@ubuntu:~$ sudo apt upgrade
```

After waiting some time, your system will be update to last versions of package.

### Installing ZSHELL
So from the OSX Catalina, I started use Zshell and I like, due the customization, but I perform a litle customization, so the first steps before replace the default shell of you system. 

```shell
youruser@ubuntu:~$ echo $SHELL
/bin/bash
youruser@ubuntu:~$ 
```

Now we will verify if have any updates avaiable to system.

```shell
youruser@ubuntu:~$ sudo apt update
```

If have you need run command below.

```shell
youruser@ubuntu:~$ sudo apt upgrade
```

Run apt to install **zhell**

```shell
youruser@ubuntu:~$ sudo apt install zsh -y
```
**OBS: When is informed the "-y" in apt command indicate that no confirmation will be need before installation.**

To confirm if *zshell* was installed run command below.
```shell
youruser@ubuntu:~$ zsh --version
zsh 5.8 (x86_64-ubuntu-linux-gnu)
youruser@ubuntu:~$ 
```

Set up **zshell** with default Shell, you first get the path of zhs installation.

```shell
youruser@ubuntu:~$ type zsh
zsh is hashed (/usr/bin/zsh)
youruser@ubuntu:~$
```

Using information above, run command below to set up the **ZSHELL** :satisfied:
```shell
youruser@ubuntu:~$ sudo usermod -s /usr/bin/zsh $(whoami)
[sudo] password for youruser: 
youruser@ubuntu:~$ 
```

To effective the *zhell* installation, perform a reboot of system, in terminal type command to restart now.
```shell
youruser@ubuntu:~$ shutdown -r now
```

After restart if message below is displayed, the **ZSHELL** is your default **SHELL** now.

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

(2)  Populate your ~/.zshrc with the configuration recommended
     by the system administrator and exit (you will need to edit
     the file by hand, if so desired).

--- Type one of the keys in parentheses --- 
```

I Prefer the manual configuration, but you can prefer automatic configuration, you follow the instructions in terminal.
Type *0* to create ***.zshrc*** empty and create your personalized configuration.

After followind the recommended configuration, a *.zshrc* file will be created in your home directory.

```shell
ubuntu% ls -ltra .zshrc
-rw-rw-r-- 1 youruser youruser 369 set 23 23:40 .zshrc
ubuntu% 
```

This steps is not necessary but I like remove the bash files.
I remove these files you can do.

```shell
ubuntu% ls -ltra .bash*
-rw-r--r-- 1 youruser youruser 3771 set 22 22:06 .bashrc
-rw-r--r-- 1 youruser youruser  220 set 22 22:06 .bash_logout
-rw------- 1 youruser youruser  727 set 23 23:27 .bash_history
ubuntu% ls -ltra .profile
-rw-r--r-- 1 youruser youruser 807 set 22 22:06 .profile
ubuntu% 
```

#### To remove run *rm* command, but take care.
#### Take care to not remove other files ok:exclamation::exclamation::exclamation:

```shell
ubuntu% rm .bash*      
ubuntu% ls -ltra .bash*
zsh: no matches found: .bash*
ubuntu% 
```
In your home directory create the empty files.
```shell
pwd
/home/yourusername
```
### The Z-Files
**.zprofile** - is sourced on all invocations of the shell, unless the -f option is set. It should contain commands to set the command search path, plus other important environment variables run command below to create empty file
```shell
touch .zprofile
```
**.zshrc** - is sourced in interactive shells. It should contain commands to set up aliases, functions, options, key bindings, etc. * run command below to create empty file
*PS: Was created automatically after installation of zshell and follow the recommended set up*

**.zshenv** - should not contain commands that produce output or assume the shell is attached to a tty. run command below to create empty file
```shell
touch .zshenv
```
**.histfile** - to save command history.

### The Powerlevel9K or 10K
So sorry I preferer the shell more clear, I'll not added this configuration here, because I'll not use powerlevel in this moment.

### Syntax highlights
I like the syntax highlight, so to added in your terminal, please make download by url, git to perform download or use command below.
```shell
sudo apt install zsh-syntax-highlighting -y
```

#### To enable the syntax run command below.
```shell
echo source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh >> ~/.zshrc
```
After command above, reload the *.zshrc* file using source command.
```shell
source .zshrc
```
### VIM or VI
So what the best editor!? I'll leave to your select what is better to you. 
So to development I use VSCode, but sometimes we need to make a little changes in some linux files or scripts, due this **VI** is the better, so to improve the use of **VI**, we can download of **VIM** and after we can create a file in ours home directory to enable some usefull configurations by default.
Performing download and Installation of **VIM**
```shell
sudo apt install vim -y
```shell
touch .vimrc
```
Create **VIM** configuration file to enable syntax.
To added **VI** syntax highlighting
```shell
echo syntax on >> .vimrc
```
To added number lines too
```shell
echo set number >> .vimrc
```
Crete alias to when your type **VI** the system call the **VIM**, in your *.zshrc* file insert the alias see exemple below.
```shell
echo alias vi='vim'
```
## I little bit of color
I like, the default scheme color of Ubuntu terminal, but when replace **bash shell** to **zshell** we lost the colors, I like when run command, example: ls and the output is displayed colored, see example:
```shell
dir --color=auto
```
But to print colored the command is big right? So in your *.zshrc* file create the alias below.
```shell
# Alias to added color outputs
alias ls='ls --color=auto'
alias dir='dir --color=auto'
alias vdir='vdir --color=auto'
alias grep='grep --color=auto'
alias fgrep='fgrep --color=auto'
alias egrep='egrep --color=auto'
```
## Identify Shell
Now we will define the **PS1** variable to display userfull information in interactive shell.
We need edit the *.zshrc* file, so added expor PS1= in the .zshrc file. See example.
```shell
export PS1="[%n@%M] "
```
Output after runned command above
```shell
[youruser@ubuntu]
```
To use this definitely, you added the configuration in your *.zshrc* file.
```shell
echo export PS1="[%n@%M] " >> .zshrc
```
Example of some options to configure PS1.

|Sequence|Printed|
|--------|-------|
|%T	    |System time (HH:MM)|
|%*	    |System time (HH:MM:SS)|
|%D	    |System date (YY-MM-DD)|
|%n	    |Current username|
|%B - %b |Begin - end bold print|
|%U - %u |Begin - end underlining|
|%d	    |The current working directory|
|%~	    |The current working directory, relative to the home directory|
|%M	    |The computer's hostname|
|%m	    |The computer's hostname (truncated before the first period)|
|%l	    |The current tty|

## WOW!!!
The terminal is ok, but have two things that's I leked.
1 - Font Fira Code
2 - Ligatures
#### Ligatures not work in Gnome Terminal, but work in VSCode and others apps**
Installing fira code font
```shell
sudo apt install fonts-firacode -y
```
To enble in Gnome Console, you need access the settings >-> Preferences >-> Profile >-> click in Custon font, and select Fira Code.

### :exclamation: :exclamation: Error in boot :exclamation: :exclamation:
I don't now, but during the boot, is returned the error below.
*Failed to ser MolListRT: Invalid Parameter
Could not create MokListRt: Invalid Parameter
Importing MOK states has failed: import_mok_state() failed
: Invalid Parameter
Continuing boot since secure mode is disabled*

#No Try This I'll review in next week

# Create root password 
```shell
sudo passwd
```
After creation of root password, your can access some directories and files that is only access by root.
```shell
rm /boot/efi/EFI/ubuntu/shimx64.efi
```
After this perform boot of system.
```shell
shutdown -r now
```

## JAVA !!!
To java you can use OpenJDK, or use Oracle, I use oracle version, so follow steps.

Add PPA repository
```shell
sudo add-apt-repository ppa:linuxuprising/java
```
A lot of text is diplayed in your terminal please click **ENTER**

```shell
sudo apt update
```
Is to verify if have any update pending
Now is time to install java
```shell
sudo apt install oracle-java11-installer-local -y
```

### To Brazilian we need add we have to add the accent
Added this command in **.zshenv**

echo "setxkbmap -model abnt -layout us -variant intl" >> .zshenv

*running the command above this configuration will be a load when the system is started*

After this configuration restart you system
```shell
shutdown -r now
```

# THE END BYE :exclamation::exclamation::exclamation:

# REFERENCES:

**ZSHELL** :arrow_right: https://linuxhint.com/install_zsh_shell_ubuntu_1804/



https://arthurgregorio.eti.br/blog/hardware/configurar-acentos-para-teclados-em-ingles-no-linux/

https://en.wikipedia.org/wiki/Comparison_of_command_shells

http://zsh.sourceforge.net/Doc/Release/zsh_toc.html

http://zsh.sourceforge.net/FAQ/zshfaq.html

http://zsh.sourceforge.net/Intro/intro_3.html

https://en.wikipedia.org/wiki/Z_shell

https://support.apple.com/en-us/HT208050

https://www.cyberciti.biz/faq/turn-on-or-off-color-syntax-highlighting-in-vi-or-vim/

https://www.cyberciti.biz/faq/howto-install-vim-on-ubuntu-linux/

https://www.cyberciti.biz/faq/vi-show-line-numbers/

https://www.cyberciti.biz/faq/turn-off-color-in-linux-terminal-bash-session/

https://wiki.gentoo.org/wiki/Zsh/Guide

https://jonasjacek.github.io/colors/

https://github.com/tonsky/FiraCode/wiki/Linux-instructions

https://blog.programster.org/ubuntu-install-fira-code-font

https://help.gnome.org/users/gnome-terminal/stable/

https://www.oracle.com/java/technologies/javase-jdk11-downloads.html

https://linuxize.com/post/install-java-on-ubuntu-18-04/

https://bugs.launchpad.net/ubuntu/+source/grub2/+bug/1867092

https://vitux.com/how-to-setup-java_home-path-in-ubuntu/

https://stackoverflow.com/questions/9612941/how-to-set-java-environment-path-in-ubuntu

http://ubuntuhandbook.org/index.php/2018/11/how-to-install-oracle-java-11-in-ubuntu-18-04-18-10/


