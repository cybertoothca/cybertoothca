
# RVM Cheat Sheet
This document describes how to use the Ruby Version Manager, rvm to manage your Ruby installations on Mac
and Linux. We use tools like rvm and nvm to avoid using sudo to install the various gems and libraries.
Do not use sudo.

## Install `rvm`

```
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
$ curl -sSL https://get.rvm.io | bash -s stable --ruby
```

See https://rvm.io/rvm/install.

## Tips And Tricks

```
$ rvm list known					# lists all of the known ruby packages
$ rvm install 2.1					# install the latest version of ruby-2.1.x
$ rvm use 2.1						# use ruby-2.1.x
$ ruby -v							# which version of ruby are you currently using
$ which ruby						# what location is the ruby binary being sourced from
$ rvm use 2.1 --default				# set the specified version to be the default version of ruby
```

See https://rvm.io/rvm/install#try-out-your-new-rvm-installation.

## Keeping `rvm` Up-to-Date

You should upgrade rvm regularly seeing as you probably don't use the tool that often.

```
$ rvm get stable
```

See https://rvm.io/rvm/upgrading

## Upgrading Ruby With `rvm`

```
$ rvm upgrade 2.1.1 2.1.2			# upgrades ruby 2.1.1 to 2.1.2, migrate gemsets, wrappers, aliases and environment files
$ rvm use 2.1.2 --default			# when upgrading you may want to use the new version as your default; not sure that the `rvm upgrade ...` command does this part
```

See https://rvm.io/rubies/upgrading

## Upgrading By Installing A New Ruby Version

I ran into a situation where I did not rvm upgrade and instead installed the latest version.  This
is fine but you may need to install the bundler for your project.

```
$ cd ~/yourRailsProject
$ rvm install 2.2.2
$ rvm use 2.2.2 --default
$ gem install bundler			# install the bundler gem
$ bundle install          # install all the gems that the project needs; notice they were not migrated over
$ rake test								# try to run your tests to ensure the upgraded ruby version is playing nice
```

# [< Home](README)
