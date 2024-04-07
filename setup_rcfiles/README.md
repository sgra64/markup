# Setting up *.bashrc* or *.zshrc* Files in $HOME Directory

&nbsp;
## Steps

1. [Step 1](#1-configure-bash-or-zsh-mac) - Configure *bash* or *zsh* (Mac)

    - configure *.bashrc* in HOME-directory

    - define PATH in *.bashrc*

2. [Step 2](#2-customize-bash-or-zsh) - Customize *bash* or *zsh* (Mac)

3. [References](#3-references)


&nbsp;
## 1. Configure *bash* or *zsh* (Mac)

Mac uses `zsh` as default command interpreter. The following applies
to `zsh` the same way, except that the configuration file `.bashrc`
is called `.zshrc` (mind the dot in front).

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
## 2. Customize *bash* or *zsh*

*bash* is widely customizable, usually by settings in *.bashrc*.

- [Bash Prompt customization](https://wiki.archlinux.org/title/Bash/Prompt_customization)

- [How to Change Colors on LS in Bash](https://linuxhint.com/ls_colors_bash)

- [How to Customize and Colorize the Bash Prompt](https://www.howtogeek.com/307701/how-to-customize-and-colorize-your-bash-prompt/)


&nbsp;
## 3. References

Good introductions to *bash* are:

- [Introduction to Bash](https://cs.lmu.edu/~ray/notes/bash).

- [Tutorial for Beginners](https://linuxconfig.org/bash-scripting-tutorial-for-beginners).

More information:

- [What is PATH?](https://en.wikipedia.org/wiki/PATH_(variable))
