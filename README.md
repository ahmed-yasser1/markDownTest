# markDownTest


## How Is The Environment Established?
When we log on to the system, the bash program starts, and reads a series of configuration scripts called startup files, which define the default environment shared by all users.

This is followed by more startup files in our home directory that define our personal environment and the exact sequence depends on the type of shell session being started.

There are two kinds:
- Login shell session.
- Non-login shell session.


## Startup files for Login Shell Sessions
1. ```/etc/profile`` - A global configuration script that applies to all users.
2. ```~/.bash_profile``` - A user's personal startup file. It can be used to extend of override settings in the global configuration script.
3. ```~/.bash_login``` - If ~/.bash_profile is not found, bash attempts to read this file.
4. ```~/.profile``` - If neither ~/.bash_profile nor ~/.bash_login is found, bash attempts to read this file. 
  + This is the default file in Debian-based distributions, such as Ubuntu.


## Startup Files for Non_Login Shell Sessions
1. ```/etc/bash.bashrc``` - A global configuration script that applies to all users.
2. ```~/.bashrc``` - A user's personal startup file. It can be used to extend or override settings in the global configuration script.

In addition to reading the startup files above, non-login shells also inherit the environment from their parent process, usually a login shell.

## How to check if the shell is login shell or non-login shell?
- if the output of the ```$0``` variable is
![$0-login](./imgs/$0-login.png)

then this shell is a login shell.

- if the output of the ```$0``` variable is
![$0_noLogin](./imgs/$0-noLogin.png)

then this shell is a non login shell.
