# Hello!!! Let's start!

In this steps by steps, I'll show my configuration to use Kubuntu 20.04 in a MacBook Pro Late 2013, I5 , 128GB SSD and 4 GB of RAM.


### Update the system.

After installation, open Konsole(Is Terminal name in KDE), and run command below.
```shell
sudo apt update
```
The output below indicate that have packages to update.
```shell
[sudo] password for landileite: 
Hit:1 http://br.archive.ubuntu.com/ubuntu focal InRelease
Hit:2 http://br.archive.ubuntu.com/ubuntu focal-updates InRelease
Hit:3 http://br.archive.ubuntu.com/ubuntu focal-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu focal-security InRelease
Reading package lists... Done
Building dependency tree       
Reading state information... Done
138 packages can be upgraded. Run 'apt list --upgradable' to see them.
```
Now run command to perform upgrade.
```shell
sudo apt upgrade -y
```
### Install GIT
Run command to install git.
```shell
sudo apt install git -y
```
The version of git installed.
```shell
youruser@kubuntu:~$ git --version
git version 2.25.1
youruser@kubuntu:~$ 
```


### Install ZSH(ZSHELL)

Installing *zshell*, for me is best shell of *Linux*.
```shell
sudo apt install zsh -y
```
To start **zshell** set up, type *zsh* in Konsole, but I prefer manually configuration of **zshell**.

If you type *zsh* this window will be displayed, is only you follow the window information to make changes.

***Type q to quit***

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20200930_134831.png" alt="drawing" width="400"/>

Version of ***zsh*** installed.
```shell
youruser@kubuntu:~$ zsh --version
zsh 5.8 (x86_64-ubuntu-linux-gnu)
youruser@kubuntu:~$ 
```

***Atention***
*If you can use the guided configuration, type **ksh** in your terminal due this the configuration window will be displayed.*

### Undestand the ZSHELL files configuration

Access your home directory *cd ~ * To confirm if you stay in your home directory.
```shell
kubuntu% pwd
/home/yourusername
kubuntu% 
```


**.zprofile** - is sourced on all invocations of the shell, unless the -f option is set. It should contain commands to set the command search path, plus other important environment variables run command below to create empty file

```shell
touch .zprofile
```

**.zshrc** - is sourced in interactive shells. It should contain commands to set up aliases, functions, options, key bindings, etc.
```shell
touch .zshrc
```

**.zshenv** - should not contain commands that produce output or assume the shell is attached to a tty. run command below to create empty file
```shell
touch .zshenv
```

**.zhistory** - to save command history.
```shell
touch .zhistory
```

Files created.
```shell
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zprofile
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zshrc
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zshenv
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zhistory
```
### My .zshrc
**History of commands**
```shell
kubuntu% echo "# History configuration" >> .zshrc
kubuntu% echo HISTSIZE=1000 >> .zshrc 
kubuntu% echo HISTFILE=~/.zhistory >> .zshrc
kubuntu% echo SAVEHIST=1000 >> .zshrc
kubuntu% 
```
File after this configuration
```shell
kubuntu% more .zshrc 
# History configuration
HISTSIZE=1000
HISTFILE=~/.zhistory
SAVEHIST=1000
kubuntu% 
```
After changes in *.zshrc* you need reload file to Konsole use the new configuration, so run command below.
```shell
kubuntu% source .zshrc 
kubuntu% 
```
To facility this, create the alias below.
```shell
echo "# My aliases" >> .zshrc
echo alias zload="'source ~/.zshrc'" >> .zshrc
```
### Syntax highlighting
To install syntax highlightin run command below.
```shell
sudo apt install zsh-syntax-highlighting -y
```
To enable syntax highlighting.
```shell
echo source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh >> ~/.zshrc
```
### Set up Zshell as default
Run command below, to dicovery the directory of installation of zsh.
```shell
kubuntu% type zsh
zsh is hashed (/usr/bin/zsh)
kubuntu%
```
To set up run command below.
```shell
kubuntu%
sudo usermod -s /usr/bin/zsh $(whoami)
kubuntu%
```
Now reboot your machine, in your terminal run command.
```shell
reboot
```

### Colorful Terminal
Syntax Highlighting


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20200930_205609.png" alt="drawing" width="150"/>

Now we can add more alias to more colors in terminal.
In your *.zshrc* file add lines below.
```shell
# Alias to added color outputs
alias ls='ls --color=auto'
alias dir='dir --color=auto'
alias vdir='vdir --color=auto'
alias grep='grep --color=auto'
alias fgrep='fgrep --color=auto'
alias egrep='egrep --color=auto'
```
Result, but before we need reload the ***.zshrc*** to effective configuration.

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20200930_210140.png" alt="drawing" width="250"/>

### VIM or VI???
I prefer *vim*, for why? For why like... :smiley:
But I use, *vim* only to quick edition of scripts and files, to create scripts and other programs I prefer **VSCode**.
Installing **vim**

```shell
kubuntu% sudo apt install vim -y
```
So after installation, we need create a file in our home called *.vimrc*
```shell
touch .vimrc
```
Add this configurations in *.vimrc* to turn on line number and syntax highlighting.
```shell
echo syntax on >> .vimrc
echo set number >> .vimrc
```

Add an alias to **vim**, to when you type **vi** system call the **vim**.
```shell
echo alias vi='vim' >> .zshrc
```

Testing if work, open a **.zshrc** file and validate that the file is colorful.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20200930_212035.png" alt="drawing" width="250"/>


### Configuration of PS1 - Prompt String One

Table of configurations possible to **zshell**

| Sequence  | Printed |
|-----------|---------|
| %T	    | System time (HH:MM)  |
| %*	    | System time (HH:MM:SS) |
| %D	    | System date (YY-MM-DD) |
| %n	    | Current username |
| %B - %b |  Begin - end bold print  |
| %U - %u |  Begin - end underlining |
| %d	    | The current working directory  |
| %~	    | The current working directory, relative to the home directory  |
| %M	    | The computer's hostname  |
| %m	    | The computer's hostname (truncated before the first period)  |
| %l	    | The current tty  |

The Configuration.

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

You can added colors in your **zshell**.

Coloar avaiable.
| Name  | Number  |
|-------|---------|
| black | 	0 |
| red 	|1  |
| green |	2 |
| yellow| 3 |
| blue 	|4  |
| magenta| 5|
| cyan 	|6|
| white | 7|

My PS1 zsh.
```shell
PS1=%F{cyan}[%n%f%F{magenta}@%M]%f %F{yellow}[%~]%f 
```

## Java from Oracle
Now we will install Java 11 LTS, I prefer Java from Oracle stead of OpenJDK. To install Java from Oracle follow steps below.

First steps is verify if have any update avaiable. If have please update, running **apt update** and after **apt upgrade**.
Verify if have updates:
```shell
sudo apt update
```
To make updates:
```shell
sudo apt upgrade
```

Now we will add repository of Oracle, run command below.
```shell
sudo add-apt-repository ppa:linuxuprising/java
```
This window will show up, please click in **ENTER**.

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_125934.png" alt="drawing" width="250"/>

Now we run two command, update and install see.
```shell
sudo apt update
```
Output indicate that new repository was add.
```shell
Hit:1 http://br.archive.ubuntu.com/ubuntu focal InRelease
........................                                      
Hit:5 http://ppa.launchpad.net/linuxuprising/java/ubuntu focal InRelease
Reading package lists... Done
Building dependency tree       
Reading state information... Done
All packages are up to date.
```

Run apt to install Java 11.
```shell
sudo apt install oracle-java11-installer-local -y
```

Follow instrunction show in window, ok?

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_131223.png" alt="drawing" width="250"/>
<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_131242.png" alt="drawing" width="250"/>

**But the installation not work the error will hapen**
```shell
please download the Oracle JDK 11 .tar.gz file
with the same version as this package (version 11.0.4),
and place it in /var/cache/oracle-jdk11-installer-local,

E.g.:
sudo mkdir -p /var/cache/oracle-jdk11-installer-local
sudo cp jdk-11.0.4_linux-x64_bin.tar.gz /var/cache/oracle-jdk11-installer-local/
sha256sum mismatch jdk-11.0.8_linux-x64_bin.tar.gz
Oracle JDK 11 is NOT installed.
```
Now in this case we need make a download of jdk 11 from Oracle site and copy to directory ***/var/cache/oracle-jdk11-installer-local/***

Make download of this file - ***jdk-11.0.8_linux-x64_bin.tar.gz***

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_200523.png" alt="drawing" width="250"/>

Copy file downloaded to directory - ***/var/cache/oracle-jdk11-installer-local***
```shell
sudo cp jdk-11.0.8_linux-x64_bin.tar.gz /var/cache/oracle-jdk11-installer-local 
```
After this run command to install jdk 11 LTS.
```shell
sudo apt-get install oracle-java11-installer-local -y
```
Output of indicate that the installation.
```shell
sudo apt-get install oracle-java11-installer-local -y
Reading package lists... Done
Building dependency tree       
Reading state information... Done
oracle-java11-installer-local is already the newest version (11.0.8-1~linuxuprising0).
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
1 not fully installed or removed.
After this operation, 0 B of additional disk space will be used.
Setting up oracle-java11-installer-local (11.0.8-1~linuxuprising0) ...
Installing from local file /var/cache/oracle-jdk11-installer-local/jdk-11.0.8_linux-x64_bin.tar.gz

You may want to remove any previous jdk .tar.gz versions from
/var/cache/oracle-jdk11-installer-local
update-alternatives: error: no alternatives for java
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jaotc to provide /usr/bin/jaotc (jaotc) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jar to provide /usr/bin/jar (jar) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jarsigner to provide /usr/bin/jarsigner (jarsigner) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/java to provide /usr/bin/java (java) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/javac to provide /usr/bin/javac (javac) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/javadoc to provide /usr/bin/javadoc (javadoc) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/javap to provide /usr/bin/javap (javap) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jcmd to provide /usr/bin/jcmd (jcmd) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jconsole to provide /usr/bin/jconsole (jconsole) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jdb to provide /usr/bin/jdb (jdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jdeprscan to provide /usr/bin/jdeprscan (jdeprscan) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jdeps to provide /usr/bin/jdeps (jdeps) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jfr to provide /usr/bin/jfr (jfr) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jhsdb to provide /usr/bin/jhsdb (jhsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jimage to provide /usr/bin/jimage (jimage) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jinfo to provide /usr/bin/jinfo (jinfo) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jjs to provide /usr/bin/jjs (jjs) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jlink to provide /usr/bin/jlink (jlink) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jmap to provide /usr/bin/jmap (jmap) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jmod to provide /usr/bin/jmod (jmod) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jps to provide /usr/bin/jps (jps) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jrunscript to provide /usr/bin/jrunscript (jrunscript) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jshell to provide /usr/bin/jshell (jshell) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jstack to provide /usr/bin/jstack (jstack) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jstat to provide /usr/bin/jstat (jstat) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/jstatd to provide /usr/bin/jstatd (jstatd) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/keytool to provide /usr/bin/keytool (keytool) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/pack200 to provide /usr/bin/pack200 (pack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/rmic to provide /usr/bin/rmic (rmic) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/rmid to provide /usr/bin/rmid (rmid) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/rmiregistry to provide /usr/bin/rmiregistry (rmiregistry) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/serialver to provide /usr/bin/serialver (serialver) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/bin/unpack200 to provide /usr/bin/unpack200 (unpack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-oracle/lib/jexec to provide /usr/bin/jexec (jexec) in auto mode
Oracle JDK 11 installed

#####Important########
To set Oracle JDK11 as default, install the "oracle-java11-set-default-local" package.
E.g.: sudo apt install oracle-java11-set-default-local
```

To validate if installation was sucess, run command below.
Verify the version of Java installed.
```shell
java -version
java version "11.0.8" 2020-07-14 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.8+10-LTS)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.8+10-LTS, mixed mode)
```
Verify the version of Javac.
```shell
javac -version
javac 11.0.8
```

## Ruby 
To use **Ruby** in Kubuntu run command below to install **Ruby**

```shell
sudo apt install ruby-full -y
```
To validate if ruby was installed with success.
```shell
ruby -v
ruby 2.7.0p0 (2019-12-25 revision 647ee6f091) [x86_64-linux-gnu]
``` 

## VSCode the best editor for me!!!
For me is the best Editor of World, change my mind!!!  (⌐■_■)
Now talking serious, for me is the best, but if you like other editor, no problem, you can install your favorite editor.

We will add repository first, run command below.
First add the Microsoft key.
The OK will be returned indicate successfull.
```shell
[youruser@kubuntu] [~] wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
OK
[youruse@kubuntu] [~] 
```

Add the repository, running command below.

```shell
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
```

Indication that the repository add are done.
```shell
Hit:1 http://br.archive.ubuntu.com/ubuntu focal InRelease
.................................                                                               
Get:6 https://packages.microsoft.com/repos/vscode stable InRelease [3.958 B]                                                             
Get:7 https://packages.microsoft.com/repos/vscode stable/main amd64 Packages [201 kB]
Fetched 312 kB in 3s (90,2 kB/s)   
Reading package lists... Done
```
Installing the **VSCode**.
```shell
sudo apt install code -y
```
To validate that installation was success, run command ***code*** in your terminal, if editor opened this indicate successfull.
```shell
code
```

## Fira Code
Who don't like Fira Code and Ligatures!?

First Step Install Fira Code. The best notice is the Fira Code works with ***Konsole*** ( ♥ ͜ʖ ♥).

Installation.
```shell
sudo apt install fonts-firacode
```

***Using Fira Code and Ligatures***

In VSCode to change the fonts we need access settings, to this press the command combination ***Control + Comma***.
This window will be open.

In field *Search Settings* type "Font".

Find field *Editor:Font Ligatures* and click in ***edit in settings.json***

This configuration will be displayed.

Add this config in file and save ***Control + s***

Testing Fira Code and Ligatures in VSCode.


#### In Konsole
To set up fira code in Konsole, click in *Settings* after click in *Edit Current Profile*.

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_232523.png" alt="drawing" width="250"/>

This window will be open.

<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_231605.png" alt="drawing" width="250"/>

In lef of window click in ***Appearence*** and in righ side of window near of bottom click in ***Choose*** to select a font.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_231635.png" alt="drawing" width="250"/>


Select font window will be opened, now in left near of bottom, click in checkbox to system show all fonts, in square font select the "Fira Code" I prefer the light style, but you can select what the best style for you, and the best size to your eyes. Click in "OK"


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_231916.png" alt="drawing" width="250"/>


Returned to this window click in "Apply" and "OK".


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/images/Screenshot_20201001_231949.png" alt="drawing" width="250"/>


Now is time to testing in your Konsole.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_232201.png" alt="drawing" width="250"/>


### # Fira Code in VSCode

Now we will configure the Fira Code and ligatures in ***VSCode***

Type ***Control*** + ***coma*** to open Settings.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201002_204919.png" alt="drawing" width="250"/>


In search bar *Search Settings* type ***font*** see example below.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_234547.png" alt="drawing" width="250"/>


Scrow down, to find option ***Editor:Font Ligatures*** and click in ***Edit in settings.json***.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201001_234611.png" alt="drawing" width="250"/>


The ***settings.json*** will be open.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201002_205632.png" alt="drawing" width="250"/>


Paste this configuration, or changer according your preferences.

```json
"editor.fontFamily": "Fira Code",
"editor.fontSize": 14,
"editor.fontLigatures": true,
```
Save setting and testing changes.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201002_210024.png" alt="drawing" width="250"/>


Changes are done, and testing with success.


<img align="center" src="https://github.com/landex/MacBook/blob/main/Kubunto_in_Mac_Pro/Kubuntu_Images/Screenshot_20201002_210104.png" alt="drawing" width="250"/>


## References:

***KUBUNTU INSTALLATION*** >>> https://userbase.kde.org/Kubuntu/Installation


***GIT*** >>> https://linuxconfig.org/how-to-install-git-on-ubuntu-20-04-lts-focal-fossa-linux


***ZSH*** >>> https://linuxhint.com/install_zsh_shell_ubuntu_1804/ 


***ZHSELL FILES*** >>> http://zsh.sourceforge.net/Intro/intro_3.html


***COLORS*** >>> https://www.cyberciti.biz/faq/turn-off-color-in-linux-terminal-bash-session/


***VIM*** >>> https://www.linode.com/docs/tools-reference/tools/introduction-to-vim-customization/


***PS1*** >>> https://wiki.gentoo.org/wiki/Zsh/Guide


***COLORS IN PS1*** >>> https://wiki.archlinux.org/index.php/zsh and http://zsh.sourceforge.net/Doc/Release/Prompt-Expansion.html#Prompt-Expansion


***JAVA*** >>> http://ubuntuhandbook.org/index.php/2018/11/how-to-install-oracle-java-11-in-ubuntu-18-04-18-10/


***RUBY*** >>> https://linuxize.com/post/how-to-install-ruby-on-ubuntu-18-04/


***VSCODE*** >>> https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-18-04/


***FIRACODE IN KUBUNTU*** >>> https://github.com/tonsky/FiraCode/wiki/Linux-instructions


***FIRACODE IN VSCODE*** >>> https://medium.com/@qjli/daily-dev-tips-96-visual-studio-code-how-to-enable-this-new-sexy-fira-code-font-89bafbfa245f

