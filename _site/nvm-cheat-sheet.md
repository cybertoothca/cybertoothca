# NVM Cheat Sheet
----

Instructions for installing the Node Version Manager on Mac or Ubuntu. The nvm tool can be
used to choose a specific version of NodeJs/npm.

## Install `nvm`

```
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```
See https://github.com/creationix/nvm#install-script.

## Tips And Tricks

```
$ nvm ls-remote                 # lists all of the available versions of NodeJs & iojs
$ nvm ls                        # list locally installed version
$ nvm install 0.12.3            # install the version 0.12.3 (see ls-remote for available options)
$ nvm use 0.12.3                # switch to and use the installed 0.12.3 version
$ nvm which 0.12.2              # the path to the installed node version
$ nvm current                   # what is the current installed nvm version
$ nvm alias default 0.10.32     # set the default node to the installed 0.10.32 version
$ nvm --help                    # the help documents
```
