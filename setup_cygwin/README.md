# Cygwin setup on *Windows*

[Cygwin](https://www.cygwin.com) is a Unix-Emulator that provides
a terminal ([mintty](https://mintty.en.lo4d.com/windows))
in which Unix commands can be executed on Windows using
*[bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell))*
(*Bourne Again Shell*) as command-line interpreter.
*bash* was developed in 1989 as a successor to the
*Bourne Shell*
*[sh](https://en.wikipedia.org/wiki/Bourne_shell)*.

Example of a
[bash terminal](https://cdn.ttgtmedia.com/rms/onlineimages/REF_bash_command_line_3.jpg).

*Cygwin* is <span style="text-decoration:underline">not</span>
a Unix system, container or virtual machine (like
[WSL](https://learn.microsoft.com/en-us/windows/wsl/about)).
*Cygwin* emulates most (but not all) Unix system calls such that
most Unix commands can be used on Windows.

[GitBash](https://gitforwindows.org)
is an alternative to *Cygwin* that uses a different emulator package
[MinGW](https://www.mingw-w64.org).
It has has some flaws, for example, it does not support symbolic links
and performs strange path conversions that may cause problems, see
[link](https://stackoverflow.com/questions/54258996/git-bash-string-parameter-with-at-start-is-being-expanded-to-a-file-path).


&nbsp;
## Steps

1. [Step 1](#1-install-cygwin) - Install *Cygwin*

2. [Step 2](#2-configure-cygwin-environment) - Configure *Cygwin* and *bash* Environment

    - switch from `/cygdrive/c` to `/c` and use Unix-rwx access (not Windows ACL)

    - select HOME-directory

    - configure *.bashrc* in HOME-directory

    - define PATH in *.bashrc*

3. [Step 3](#3-customize-bash) - Customize *bash*

4. [References](#4-references)


&nbsp;
## 1. Install Cygwin

1. Download the installer `setup-x86_64.exe` from
[https://www.cygwin.com/install.html](https://www.cygwin.com/install.html).


1. Run the installer `setup-x86_64.exe`.

    - select useful tools from packages (check boxes):
        - Editors/`vim` - visual editor,
        - Web/`wget` - web downloader,
        - Net/`curl` - web downloader.


1. Change *cygwin* default path `/cygdrive/c` to: `/c` and use Unix *rwx* - access
    (not Windows ACL):

    - navigate to the *cygwin* installation directory called `cygwin64`.

    - inside, edit `/etc/fstab` and replace line
        ```
        none /cygdrive cygdrive binary,posix=0,user 0 0

        with:
        none / cygdrive binary,posix=0,user,noacl 0 0
        ```


1. Add bash-user that works with Windows and create *bash* HOME directory.

    - Find out your Windows user name: <user_name>

    - Create or select a directory to use as HOME-directory for
      *bash*, e.g. your Windows HOME-directory `C:\Users\<user_name>`
      (but also any other directory you may create as HOME).

      Read
      [Change Cygwin home folder after installation](https://stackoverflow.com/questions/1494658/how-can-i-change-my-cygwin-home-folder-after-installation).

    - Edit file `/etc/nsswitch.conf`:
        - to use your Windows HOME-directory, comment line (put hash # in front)
            ```
            #db_home:
            ```
        - to use a different HOME directory `<path>`, enter
            ```sh
            db_home: /c/<path>      # e.g. db_home: /c/users/svgr
            ```


1. Create a terminal icon on your Desktop.

    - In the installation directory (`cygwin64`), navigate to `./bin`
        and find file
        [mintty.exe](https://en.wikipedia.org/wiki/Mintty),
        which is the terminal emulator executable.

    - Create a shortcut for *mintty.exe*
        (right-click file -> Create Shortcut -> On Desktop).
        The terminal icon appears on your desktop.


1. Open *mintty* terminal and test:

    ```sh
    $ whoami
    <user_name>         # your user name appears

    $ echo $HOME        # print path to HOME-directory
    <home_directory>    # output, e.g. /c/Users/svgr

    $ cd $HOME          # change into HOME-directory
    $ ls -la            # show content
    total 203
    drwxr-xr-x+ 1 svgr2 Kein      0 Oct  4 22:20 .
    drwxrwx---+ 1 svgr2 Kein      0 Jan  1  2022 ..
    -rw-------  1 svgr2 Kein  14476 Oct  4 22:20 .bash_history
    -rwxr-xr-x+ 1 svgr2 Kein   2717 Oct  4 20:28 .bashrc
    ...

    $ echo Hello >hello.txt     # create file hello.txt with content Hello
    $ ls -la                    # show new file exists in $HOME
    total 203
    -rw-r--r--  1 svgr2 Kein      6 Oct  7 23:38 hello.txt
    ...

    $ cat hello.txt             # output content of file
    Hello
    ```


1. Open Windows file explorer (
    [ ? ](https://geekflare.com/wp-content/uploads/2021/06/14-alternative-file-managers-to-replace-windows-10-file-explorer.jpg)
    ) and navigate to file `hello.txt`.
    Open the file by clicking (ending `.txt` should open the
    file with *notepad*).


1. Return to *bash* terminal:
    - change to HOME-directory and
    - show content of file `.bashrc` using a text editor:
        *[vim](https://www.vim.org)* (already installed with cygwin),
        *[nano](https://www.nano-editor.org)* or
        *[sublime](https://www.sublimetext.com)*
        are good choices.
        ```sh
        $ cd            # change to bash HOME-directory
        $ ls -la        # find file .bashrc
        total 203
        -rwxr-xr-x+ 1 svgr2 Kein   2717 Oct  4 20:28 .bashrc

        $ cat .bashrc   # output file .bashrc
        content of file .bashrc appears...
        ```


&nbsp;
## 2. Configure *Cygwin* Environment

[PATH](https://en.wikipedia.org/wiki/PATH_(variable)) is an
environment variable on Unix-like operating systems that
specifys a set of directories where executable programs are
located. A *"command not found"* error occurs when PATH is
not properly configured.


1. Inspect the current PATH variable on your system:
    ```sh
    echo $PATH
    .:/usr/bin:/usr/local/bin:/c/WINDOWS:/c/WINDOWS/system32: ...
    ```
    PATH has a list of directory paths starting from the root directory '/'
    separated by colon ( : ).

    To print PATH more readable, replace ( : ) by newlines:
    ```sh
    echo $PATH | tr ':' '\n'
    .
    /usr/bin
    /usr/local/bin
    /c/WINDOWS
    /c/WINDOWS/system32
    ...
    ```
    Make sure these paths are included in PATH.


1. Open `.bashrc` using a text editor
    (*[sublime](https://www.sublimetext.com)* or
    *[vim](https://www.vim.org)* - already installed with
    *cygwin* - are good choices).
    Append lines for PATH configurations at the end.
    ```sh
    $ vim .bashrc       # open file .bashrc in vim editor
    ```
    or drag file from file explorer into sublime for editing.


1. Append following PATH configurations at the end of the file -
    only those relevant on your system adjusted for your system:

    ```sh
    # add Windows system paths
    export PATH=".:/usr/bin:/usr/local/bin"
    export PATH="${PATH}:$(cygpath ${SYSTEMROOT}):$(cygpath ${SYSTEMROOT})/system32"

    # if Java, add Java path (as first entry on PATH)
    # make sure the path to Java exists on your system and is the path
    # to a JDK (Java Development Kit) and not JRE, which is just the
    # Java Runtime that has no compiler, no javadoc or jar.
    export JAVA_HOME="/c/Program Files/Java/jdk-21"
    export PATH="${JAVA_HOME}/bin:${PATH}"

    # if Python, add Python path
    export PYTHON_HOME="/c/Users/svgr2/AppData/Local/Programs/Python/Python312"
    export PATH="${PATH}:${PYTHON_HOME}"
    export PATH="${PATH}:${PYTHON_HOME}/Scripts"

    # if Docker, add Docker path
    export DOCKER_HOME="/c/Program Files/Docker/Docker"
    export PATH="${PATH}:${DOCKER_HOME}/resources/bin"
    ...
    ```


1. Verify paths have been added to *PATH* variable:
    ```sh
    $ source .bashrc    # reload .bashrc to activate PATH definitions
    $ echo ${PATH}                      # show PATH
    .:/usr/bin:/usr/local/bin:/c/WINDOWS:/c/WINDOWS/system32:/c/Program ...

    $ echo ${$PATH} | tr ':' '\n'       # pretty print PATH
    .
    /c/Program Files/Java/jdk-21/bin    <-- path to JDK executables
    /usr/bin
    /usr/local/bin
    /c/WINDOWS
    /c/WINDOWS/system32
    ...
    ```
    Paths may vary based on your system.


1. Start programs to verify paths have properly been set.

    ```sh
    $ java --version
    java 21 2023-09-19 LTS
    Java(TM) SE Runtime Environment (build 21+35-LTS-2513)
    Java HotSpot(TM) 64-Bit Server VM (build 21+35-LTS-2513, mixed mode, sharing)

    $ python --version
    Python 3.12.0

    $ docker --version
    Docker version 24.0.6, build ed223bc
    ```


&nbsp;
## 3. Customize *bash*

*bash* is widely customizable, usually by settings in *.bashrc*.

- [Bash Prompt customization](https://wiki.archlinux.org/title/Bash/Prompt_customization)

- [How to Change Colors on LS in Bash](https://linuxhint.com/ls_colors_bash)

- [How to Customize and Colorize the Bash Prompt](https://www.howtogeek.com/307701/how-to-customize-and-colorize-your-bash-prompt/)


&nbsp;
## 4. References

Good introductions to *bash* are:

- [Introduction to Bash](https://cs.lmu.edu/~ray/notes/bash).

- [Tutorial for Beginners](https://linuxconfig.org/bash-scripting-tutorial-for-beginners).

More information:

- [Differences between Cygwin and MinGW](https://stackoverflow.com/questions/771756/what-is-the-difference-between-cygwin-and-mingw)

- [Change Cygwin HOME directory after installation](https://stackoverflow.com/questions/1494658/how-can-i-change-my-cygwin-home-folder-after-installation).

- [What is PATH?](https://en.wikipedia.org/wiki/PATH_(variable))
