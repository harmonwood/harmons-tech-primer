# Ruby Environments

## Install chruby and ruby-install

```sh
brew install ruby-install chruby
```

### Modify zshrc for binary and auto switching

```sh
#Add the following to the ~/.bash_profile or ~/.zshrc file:
source /opt/homebrew/opt/chruby/share/chruby/chruby.sh

#To enable auto-switching of Rubies specified by .ruby-version files,
#add the following to ~/.bash_profile or ~/.zshrc:
source /opt/homebrew/opt/chruby/share/chruby/auto.sh
```

## Install latest Ruby

This will install ruby

```sh
ruby-install --update ruby
```

Now to link it add this to your ~/.zshrc file. Remember to change the home and version.

```sh
export PATH="/Users/<home>/.rubies/ruby-<version>/bin:$PATH"
```

## Start using Ruby in a project

Create a .ruby-version file in the root of your project and add the version you want to use.

chruby will now automaticly switch to the version in the .ruby-version file when you enter the directory.

```sh
echo "ruby-3.2.2" > .ruby-version
```

## Install bundler

```sh
gem install bundler
```

## Install gems

```sh
bundle install
```
