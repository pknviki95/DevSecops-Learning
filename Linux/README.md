# Linux

## Topics:

- Linux Basic concepts
- System documentation
- Linux Filesystems
- Linux Paths
- Working with files and directories


## Linux Basic concepts:

### Operating system:

- An operating system is a program that acts as an interface between the user and the computer hardware  
- It controls the execution of all kinds of programs. 

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/Linux/Images/OS.jpeg)

## System documentation:

### [command] --help:

- --help option is used to **list down all posibble options of given command and its usage with short explanation**

            [command] --help

            pknviki95@ubuntu18:~/pknviki$ mkdir --help
            Usage: mkdir [OPTION]... DIRECTORY...
            Create the DIRECTORY(ies), if they do not already exist.

            Mandatory arguments to long options are mandatory for short options too.
            -m, --mode=MODE   set file mode (as in chmod), not a=rwx - umask
            -p, --parents     no error if existing, make parent directories as needed
            -v, --verbose     print a message for each created directory
            -Z                   set SELinux security context of each created directory
                                    to the default type
                --context[=CTX]  like -Z, or if CTX is specified then set the SELinux
                                    or SMACK security context to CTX
                --help     display this help and exit
                --version  output version information and exit

            GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
            Full documentation at: <http://www.gnu.org/software/coreutils/mkdir>
            or available locally via: info '(coreutils) mkdir invocation'

### Manual page(man [command]):

- man command **returns the manual page of the commands listed with detailed explanation on description section**

            man [command]

- man command can be used to **read specific section of commands by passing its section number** 
- section number is based from **1-9**

            man [section number] [command]

            MAN(1)                                                                                    Manual pager utils                                                                                    MAN(1)

            NAME
                man - an interface to the on-line reference manuals

            SYNOPSIS
                man [-C file] [-d] [-D] [--warnings[=warnings]] [-R encoding] [-L locale] [-m system[,...]] [-M path] [-S list] [-e extension] [-i|-I] [--regex|--wildcard] [--names-only] [-a] [-u] [--no-sub‐
                pages] [-P pager] [-r prompt] [-7] [-E encoding] [--no-hyphenation] [--no-justification] [-p string] [-t] [-T[device]] [-H[browser]] [-X[dpi]] [-Z] [[section] page[.section] ...] ...
                man -k [apropos options] regexp ...
                man -K [-w|-W] [-S list] [-i|-I] [--regex] [section] term ...
                man -f [whatis options] page ...
                man -l [-C file] [-d] [-D] [--warnings[=warnings]] [-R encoding] [-L locale] [-P pager] [-r prompt] [-7] [-E encoding] [-p string] [-t] [-T[device]] [-H[browser]] [-X[dpi]] [-Z] file ...
                man -w|-W [-C file] [-d] [-D] page ...
                man -c [-C file] [-d] [-D] page ...
                man [-?V]

            DESCRIPTION
                man is the system's manual pager.  Each page argument given to man is normally the name of a program, utility or function.  The manual page associated with each of  these  arguments  is  then
                found  and  displayed.   A section, if provided, will direct man to look only in that section of the manual.  The default action is to search in all of the available sections following a pre-
                defined order ("1 n l 8 3 2 3posix 3pm 3perl 3am 5 4 9 6 7" by default, unless overridden by the SECTION directive in /etc/manpath.config), and to show only the first page found, even if page
                exists in several sections.

                The table below shows the section numbers of the manual followed by the types of pages they contain.

                1   Executable programs or shell commands
                2   System calls (functions provided by the kernel)
                3   Library calls (functions within program libraries)
                4   Special files (usually found in /dev)
                5   File formats and conventions eg /etc/passwd
                6   Games
                7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
                8   System administration commands (usually only for root)
                9   Kernel routines [Non standard]

                A manual page consists of several sections.

#### apropos [command]:

- apropos used for **searching for commands through man pages**
- It skims through **all the man pages with the above command/word that you pass and returns the command related to that man page**

                apropos [command]

                pknviki95@ubuntu18:~/pknviki$ apropos director
                addgnupghome (8)     - Create .gnupg home directories
                alphasort (3)        - scan a directory for matching entries
                basename (1)         - strip directory and suffix from filenames
                bf_compact (1)       - shell script to compact a bogofilter directory
                bf_compact-bdb (1)   - shell script to compact a bogofilter directory
                bf_copy (1)          - shell script to copy a bogofilter working directory
                bf_copy-bdb (1)      - shell script to copy a bogofilter working directory
                bf_tar (1)           - shell script to write a tar file of a bogofilter directory to stdout
                bf_tar-bdb (1)       - shell script to write a tar file of a bogofilter directory to stdout
                bindtextdomain (3)   - set directory containing message catalogs
                chacl (1)            - change the access control list of a file or directory
                chdir (2)            - change working directory
                chroot (2)           - change root directory

- To get **return value of commands from specfic section of man pages using -s option**

                apropos -s [section number] [command]

                pknviki95@ubuntu18:~/pknviki$ apropos -s 2 director
                chdir (2)            - change working directory
                chroot (2)           - change root directory
                execveat (2)         - execute program relative to a directory file descriptor
                fchdir (2)           - change working directory
                futimesat (2)        - change timestamps of a file relative to a directory file descriptor
                getcwd (2)           - get current working directory
                getdents (2)         - get directory entries
                getdents64 (2)       - get directory entries
                lookup_dcookie (2)   - return a directory entry's path
                mkdir (2)            - create a directory
                mkdirat (2)          - create a directory
                readdir (2)          - read directory entry
                rmdir (2)            - delete a directory


Note: **If the machine is ran for the first time it throws error as we haven't updated the man database**

                [bob@centos-host ~]$ apropos ssh
                ssh: nothing appropriate.

- To resolve the above issue run below command            
                
                sudo mandb

#### tab suggestion/auto completion:

- tab button return **the various possiblities of commands/option with their auto-completion**
- Based on the list it makes **easier for us to update the commands in faster way**

                [command]+tab

                pknviki95@ubuntu18:~/pknviki$ systemctl li
                link               list-dependencies  list-jobs          list-machines      list-sockets       list-timers        list-unit-files    list-units 

## Linux Filesystems:

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/Linux/Images/Linuxfilesystem.jpg)

/ (root directory):
--------------------

- The **/** refers to the **root directory**
- The root directory is the **one from which all other directories branch off from**. 
- When you run tree and tell it to start with /, you will see the whole directory tree, all directories and all the subdirectories in the whole system, with all their files, fly by.

/bin:
-----

- /bin is the directory that contains **binaries, that is, some of the applications and programs you can run**. 
- You will find the ls program mentioned above in this directory, as well as other basic tools for making and removing files and directories, moving them around, and so on. 
- There are more bin directories in other parts of the file system tree, but we’ll be talking about those in a minute.

/boot:
--------

- The /boot directory contains **files required for starting your system**. 
- Do I have to say this? Okay, I’ll say it: DO NOT TOUCH!. If you mess up one of the files in here, you may not be able to run your Linux and it is a pain to repair. 
- On the other hand, don’t worry too much about destroying your system by accident: **you have to have superuser privileges to do that (i.e) sudo**.

/dev:
------

- /dev contains **device files**. 
- Many of these are generated at **boot time or even on the fly**. 
- For example, **if you plug in a new webcam or a USB pendrive into your machine, a new device entry will automatically pop up here**.

/etc:
-----

- /etc is the directory contains **system-wide configuration files**. 
- For example, **the files that contain the name of your system, the users and their passwords, the names of machines on your network and when and where the partitions on your hard disks should be mounted** are all in here. 

/home:
-------

- /home contains **users’ personal directories**. 
- In our case, under /home there are two directories: /home/pknviki95, which contains all my stuff; and /home/guest, in case anybody needs to borrow my computer.

/lib:
------

- /lib contains **libraries**. 
- Libraries are **files containing code that your applications can use. They contain snippets of code that applications use to draw windows on your desktop, control peripherals, or send files to your hard disk**.
- There are more lib directories around the file system, but this **one is directly on / , it contains the all-important kernel modules. The kernel modules are drivers that make things like your video card, sound card, WiFi, printer, and so on, work.**

/media:
--------

- The /media contains **external storage will be automatically mounted when you plug it in and try to access it**. 
- As opposed to most of the other items on this list, /media does not hail back to 1970s, mainly because inserting and detecting storage (pendrives, USB hard disks, SD cards, external SSDs, etc) on the fly, while a computer is running, is a relatively new thing.

/mnt:
--------

- The /mnt contains **manually mounted storage devices or partitions**.

/opt:
------

- The /opt contains **the binaries and libraries for the software you compile (that is, you build yourself from source code and do not install from your distribution repositories).**
- **Applications will end up in the /opt/bin directory and libraries in the /opt/lib directory**.

NOTE: another place where applications and libraries end up in is /usr/local, When software gets installed here, there will also be /usr/local/bin and /usr/local/lib directories. What determines which software goes where is how the developers have configured the files that control the compilation and installation process.

/proc:
--------

- The /proc contains **information about your computer, such as information about your CPU and the kernel your Linux system is running**.

/root:
------

- /root is the **home directory of the superuser (also known as the “Administrator”) of the system**. 
- It is separate from the rest of the users’ home directories BECAUSE YOU ARE NOT MEANT TO TOUCH IT. Keep your own stuff in your own directories.

/run:
---------

- /run directory. **System processes use it to store temporary data for their own nefarious reasons**. This is another one of those DO NOT TOUCH folders.

/sbin:
-------

- /sbin is **similar to /bin, but it contains applications that only the superuser (hence the initial s) will need**. 
- You can use these applications with the sudo command that temporarily concedes you superuser powers on many distributions. 
- /sbin typically contains **tools that can install stuff, delete stuff and format stuff. As you can imagine, some of these instructions are lethal if you use them improperly, so handle with care.**

/usr:
------

- /usr contains **a mish-mash of directories which in turn contain applications, libraries, documentation, wallpapers, icons and a long list of other stuff that need to be shared by applications and services**.
- The /usr directory was where users’ home directories were originally kept back in the early days of UNIX. However, now /home is where users kept their stuff as we saw above. 
- You will also find bin, sbin and lib directories in /usr.
- Originally, the **/bin directory (hanging off of root) would contain very basic commands, like ls, mv and rm; the kind of commands that would come pre-installed in all UNIX/Linux installations, the bare minimum to run and maintain a system**. 
- /usr/bin on the other hand would **contain stuff the users would install and run to use the system as a work station, things like word processors, web browsers, and other apps.**
- But many modern Linux distributions just put everything into /usr/bin and have /bin point to /usr/bin just in case erasing it completely would break something. So, while Debian, Ubuntu and Mint still keep /bin and /usr/bin (and /sbin and /usr/sbin) separate; others, like **Arch and its derivatives just have one “real” directory for binaries, /usr/bin, and the rest or *bins are “fake” directories that point to /usr/bin.

/srv:
-----

- The /srv directory contains **data for servers**. 
- If you are running a web server from your Linux box, your HTML files for your sites would go into /srv/http (or /srv/www). If you were running an FTP server, your files would go into /srv/ftp.

/sys:
------

- /sys is another virtual directory like /proc and /dev and also contains **information from devices connected to your computer**.
- In some cases you can also **manipulate those devices**. 
- for example, change the brightness of the screen of my laptop by modifying the value stored in the /sys/devices/pci0000:00/0000:00:02.0/drm/card1/card1-eDP-1/intel_backlight/brightness file (on your machine you will probably have a different file). But to do that you have to become superuser. The reason for that is, as with so many other virtual directories, messing with the contents and files in /sys can be dangerous and you can trash your system. DO NOT TOUCH until you are sure you know what you are doing.

/tmp:
-------

- /tmp contains **temporary files, usually placed there by applications that you are running**. 
- **The files and directories often (not always) contain data that an application doesn’t need right now, but may need later on**.
- You can also use **/tmp to store your own temporary files — /tmp is one of the few directories hanging off / that you can actually interact with without becoming superuser**.

/var:
-----

- /var contains **variable data files**. 
- /var contains things like **logs in the /var/log subdirectories**. 
- Logs are **files that register events that happen on the system**. 
- for example, If something fails in the kernel, it will be logged in a file in /var/log; if someone tries to break into your computer from outside, your firewall will also log the attempt here. 
- It also contains **spools(output) for tasks**. These “tasks” can be the jobs you send to a shared printer when you have to wait because another user is printing a long document, or mail that is waiting to be delivered to users on the system.

/snap:
------

- The /snap directory contains **all the files and the software installed from snaps**.
- Ubuntu has recently incorporated snap packages as a way of distributing software. 

## Linux Paths:

- **Absolute path**
- **Relative path**

### Absolute path:

- Absolute path is **specifying the path of the file from the root directory (/)**  
- It is usually complete path of the file system from root directory

                [command] [absolute path]

                pknviki95@ubuntu18:/$ cd /home/pknviki95/pknviki/study/DevSecops-Learning/
                Docker/             .git/               GIT/                Grafana/            Jenkins/            Kubernetes/         Linux/              NetworkingConcepts/ Prometheus/         Yaml/
        
### Relative path:

- Relative path is **specifying the file based on present working directory** 
- It usually starts with **current working directory and not from (/) root directory** 

                [command] [relative path]

                pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning$ pwd
                /home/pknviki95/pknviki/study/DevSecops-Learning

                pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning$ cd ../Devops_study_material/LINUX/
                Interview/    PDF/          Script_study/ 

#### tree:

- To list down the **tree of directories in linux filesystems**
- The level of tree to list can be defined by -L option

                tree -L [Number]

                pknviki95@ubuntu18:/$ tree -L 1
                .
                ├── bin
                ├── boot
                ├── cdrom
                ├── dev
                ├── etc
                ├── home
                ├── initrd.img -> boot/initrd.img-5.4.0-150-generic
                ├── initrd.img.old -> boot/initrd.img-5.4.0-149-generic
                ├── lib
                ├── lib64
                ├── lost+found
                ├── media
                ├── mnt
                ├── opt
                ├── proc
                ├── root
                ├── run
                ├── sbin
                ├── snap
                ├── srv
                ├── sys
                ├── tmp
                ├── usr
                ├── var
                ├── vmlinuz -> boot/vmlinuz-5.4.0-150-generic
                └── vmlinuz.old -> boot/vmlinuz-5.4.0-149-generic

                22 directories, 4 files

## Working with files and directories:

### Present working directory(pwd):

- It returns the **current working directory path**

                pwd

                pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning$ pwd
                /home/pknviki95/pknviki/study/DevSecops-Learning

### change directory(cd [absolute/relative path]):

- It is used to **change directory from present working directory.***

#### cd ..:

- It is used to **change directory to parent of present working directory.**
- **..** refers to **parent directory**

                pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning$ pwd
                /home/pknviki95/pknviki/study/DevSecops-Learning
                pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning$ cd ..
                pknviki95@ubuntu18:~/pknviki/study$ pwd
                /home/pknviki95/pknviki/study

#### cd /:


- It is used to **change directory to root directory.**
- **/** refers to **root directory**

                pknviki95@ubuntu18:~/pknviki/study$ pwd
                /home/pknviki95/pknviki/study
                pknviki95@ubuntu18:~/pknviki/study$ cd /
                pknviki95@ubuntu18:/$ pwd
                /

#### cd ~:

- It is used to **change directory to home directory.**
- **~** refers to **home directory**

                pknviki95@ubuntu18:/$ pwd
                /
                pknviki95@ubuntu18:/$ cd ~
                pknviki95@ubuntu18:~$ pwd
                /home/pknviki95

#### cd -:

- It is used to **change directory to previous directory.**
- **-** refers to **previous directory**

                pknviki95@ubuntu18:~/pknviki/study$ pwd
                /home/pknviki95/pknviki/study
                pknviki95@ubuntu18:~/pknviki/study$ cd ~
                pknviki95@ubuntu18:~$ cd -
                /home/pknviki95/pknviki/study
                pknviki95@ubuntu18:~/pknviki/study$

### Listing of files/directory(ls):

- **Listing of files and directories in a given relative/absolute path.**

                pknviki95@ubuntu18:~/pknviki$ ls
                Dockerfile  Funds_india  Germany  index.html  info.txt  minikube-linux-amd64  Practices  sonar.tar  study  text.txt  tools

#### ls -a, --all:
  

- **List all the files/directories in the diectory (including hidden files)**

#### ls -l:

- **List all the files/directories in the diectory with a long listing format (i.e) file permission,user-id,group-id,filename,size of file,last modified**

                pknviki95@ubuntu18:~/pknviki$ ls -al ~
                total 258388
                drwxr-xr-x 43 pknviki95 pknviki95      4096 Jun 29 22:44 .
                drwxr-xr-x  4 root      root           4096 Dec 25  2022 ..
                drwxr-xr-x  3 pknviki95 pknviki95      4096 Sep 28  2022 .anydesk
                -rw-------  1 pknviki95 pknviki95     44168 Jun 29 14:50 .bash_history
                -rw-r--r--  1 pknviki95 pknviki95       220 May 19  2022 .bash_logout
                -rw-r--r--  1 pknviki95 pknviki95      4104 Mar 23  2023 .bashrc


#### ls -s, --size:
 
- **List all the files/directories in the diectory with Printing the allocated size of each file, in blocks**

#### ls -h, --human-readable:

- **List all the size of files/directories with human readable format -l and/or -s, print human readable size (e.g., 1K 234M 2G)**

                pknviki95@ubuntu18:~/pknviki$ ls -lsh
                total 669M
                4.0K -rw-rw-r--  1 pknviki95 pknviki95  143 Mar 26  2023 Dockerfile
                4.0K drwxrwxr-x  2 pknviki95 pknviki95 4.0K Dec 14  2022 Funds_india
                4.0K drwxrwxr-x  3 pknviki95 pknviki95 4.0K Dec 25  2022 Germany
                4.0K -rw-rw-r--  1 siva      pknviki95  327 Mar 26  2023 index.html
                4.0K -rw-rw-r--  1 pknviki95 pknviki95 1.2K Mar 28  2023 info.txt
                78M -rw-rw-r--  1 pknviki95 pknviki95  78M Mar 19  2023 minikube-linux-amd64

                (i.e)[size] [permission] [user] [group] [human-readable] [last modified] [filename]