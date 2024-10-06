## 4. *Dotfiles*

Topics:
- a) [What are *Dotfiles*?](#a-what-are-dotfiles)
- b) [Role of *profile*, *rc* and *logout* files](#b-role-of-profile-rc-and-logout-files)
- c) [Execution order](#c-execution-order)
- d) [History files](#d-history-files)
- e) [*Sourcing* dotfiles](#e-sourcing-dotfiles)


---
&nbsp;
### a) What are *Dotfiles*?

"Dotfiles" are files (or directories with files) with names that start
with a dot `[.]`. They contain vital setup and configuration information
for the system and for tools. Most dotfiles are stored in the user's
`$HOME` directory.

On most systems, dotfiles are "hidden" (not visible) in the filesystem by default. To show them, follow instructions for Mac or Windows.


---
&nbsp;
### b) Role of *profile*, *rc* and *logout* files

Prominent dotfiles are *.profile*, *.zprofile* (Mac) in a User's `$HOME`
directory that automatically run *on Login* (or a new terminal is opened)
and *.bashrc*, *.zshrc* (Mac) that run when a *new shell process starts*.

*"Profile"* scripts run upon startup, login, when a new terminal is opened
or after login in a remote system (a remote machine or local or remote
virtual machines or containers).

*"Profile"* perform tasks that last for the entire session and can be
inhertited (*"exported"*) to sub-processes (e.g. *shells*).

*"rc-files"* execute evertime a new *shells* starts and their impact
should is valid for the existence of the *shell* process only and
can be exported to sub-processes of the *shell* process.

*"logout"* execute when a session (a terminal) is closed.


---
&nbsp;
### c) Execution order

Before *profile* and *rc-files* from the User's `$HOME` directory, system-wide
files execute that are hosted in the `/etc` (pronounce: *et'see*) directory.

```
/etc/profile
```

Exact execution order of *profile*, *rc-* and *logout-* files varies for *shells*.

The chart shows the full execution path for *bash* (source: [3]):

<img src="https://mermaid.ink/img/pako:eNq9VV1v0zAU_SuWxd6SlYxtQJGQGBRtUhlolXhgRpObuKlVx65sB6lqu9-OP5LUcYK0J_LQ2veee318fK-9h7koCJzCNE0R11QzMgU3WK2B0ljqegtWlBGFuPOXEm_XYP6AODAfo3yz0DtGQEFWuGbaxEixIVMD2yHuQUuTa4-gTYngsbUyUVJuzHP77-zWygWfN457wVPWc1KuicS5pn-I8d-dZmH4XQ9kk9AIeGIF0vSjJxLZWho9ss4TJotc_cX7-xmP7XnHwmOVL1p9gSTFh9j7pvMKiXlJBoDLDlBKQvjAf9X5l6y24R6gdkqTaqbzH1LYWnhEcEJ0Ptn6KYK_Q9ytqMgJ-Dw5D2EeaIIf8jaLFf3c_si8y2TsRhhR6wHoiTl7kGwdr-dgMTeLcloHmKa6AoRj1bgDOk2w5xNEt0QsZnb_0zhf3Xxa3D6ZcUDw7Aws1tgcGMCV4KXSVnHbUE6zeulbyub8SqXS31fg0Q2AWDW57VdQSUxlCN41X7T5vnF-qurRo2l05gXiAU-nSDIs1MDgajWuCGcMdtAsbKwHQ9grdQhkdPjukOMyvE7eJu-S91GtxyR51NojF8B_4Jq9TrIsyS6SbKT7Osq8vcteoK1rDjfyFTlY8TLJrgaNPLbUSxWy5Rovct27CnpF8lkKpVIlaplTXo5fEU7OXFSm4NkOOCxRB7-3Qdv-A-y3DxNYEVlhWpgnam9jEdRrUpnWnpphgeUGQcSPBodrLRY7nsPpCjNFElhvC6zJF4pNi1WRdVZQLWRnJG76zb-E7kFM4BbzX0K0gce_ZDNlBw?type=png" width="600"/>

This chart shows the execution path for *zsh* (Mac) (source: [3]):

<img src="https://mermaid.ink/img/pako:eNq9VduK2zAQ_RUjWGhh3Ky82dwKfWpgF9JSkrfUfVBtJTGxpSDLgTSbfnt1sR1LTpelDw2ESHPOSCdHo9EZJTylaIbCMIyZzGROZ8F69RSUkghZHYJNltMyZgbeCnLYBYtlzAL1yTO2X8lTToOUbkiVS5Uj-J7OFO0UM0v6Ve7OMVqXuxhdmljOtxlT0YX-NXEdZZwtauArZ2HugBmTVJBEZkeq8OfrrJv-7JD0IplHbDUFYfjJ6nBDjQhHqkG6S3mQu7X7b27nOqif7rsbNb4GgqYfffShRbkgbEt7hGFL2ApKWQ9_bPGfeaXTLYHKZM6O32M0UKOB8kd_KTvG6EdL-Ca4Lg-HdLCxLm2ZeMuIpAsbJxxGffYOhVfS56iQIVnajhfUKv49-OBp1dhVrMZ9mZphdNrkjkKNNBI16IqrUauuhl1d5amUtJj33PIVWN6Tr7SmBe8YVxeMVyKh6fvO8nd3thKhX2W9gCk3e7BmWFvmgvXuZuprb7PquZu5TFp8mbjQtdpbO6-EF84Ca9tLx89OqjbUq9oRjGECU8D3gDHgCPAD4CHgR8Aj7774PjGvMdxoH__Frr96oqT-qy14DHgCeArRPUQYogiiGw2i3YY1jfb16nmTETdOv9PDhhA9QjSCaNxrR7fUvOGMXhXV2XkC0dRvcQhQQUVBslS9fGedEiO5o4W6jTM1TInYxyhmF8UjleSrE0vQbEPykgKqDimR9HNG1DNXeNF5mkku2iA10y_2gTXvLKADYWvOm8TLH1AudVE?type=png" width="600"/>

More detail can be found in [3].


---
&nbsp;
### d) History files

*History-files*, e.g. `.bash_history` store typed commands as a conseutive list.
They can be recalled by the `history` command to avoid double typing.

*History-files* are also stored in the User's `$HOME` directory. They are
automatically created by *Shells*.

Prompts usually indicate the command number under which a file is stored in the
*history-file*.


---
&nbsp;
### e) *Sourcing* dotfiles

*"Sourcing"* dotfiles (or any script) refers to the *Shell* command:
[*source*](https://linuxcommand.org/lc3_man_pages/sourceh.html).

```sh
$ source ~/.bashrc          # sourcing the .bashrc file executes commands by the
                            # same shell process.
```

Commands from the script are executed *within* the context of the same
*Shell* and are therefore effective for this *Shell* making changes
to environment variables, e.g. `export PATH+=":/bin/java/jdk-21/bin"`
effective for the terminal *Shell*.

In contrast, for *script execution* (without `source`), the terminal *Shell*
will create a sub-process (a *child-Shell* process) execute the script.
Changes to the environment (e.g. to `$PATH`) will be effecitve in the
*child-process* only and *not propagate back* to the parent *Shell* in
the terminal.

```sh
$ cleanup.sh                # commands of the 'cleanup,.sh' script are executed
                            # by a sub-process (child-shell)
```


&nbsp;
---
### References

- [1] Dionysia Lemonaki:
    [*What are Dotfiles?*](https://www.freecodecamp.org/news/dotfiles-what-is-a-dot-file-and-how-to-create-it-in-mac-and-linux/),
    (2021).

- [2] *A Curated List of Awesome Dotfiles*,
    [[*link*]](https://github.com/webpro/awesome-dotfiles).

- [3] Stackoverflow, *Complete overview of Bash and Zsh startup files sourcing order*, 
    [[*link*]](https://superuser.com/questions/1840395/complete-overview-of-bash-and-zsh-startup-files-sourcing-order)

---
&nbsp;
