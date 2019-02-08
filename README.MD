# PKS CLI zsh complete plugin
This [zsh](http://www.zsh.org/) plugin adds autocompletion options for all PKS CLI Commands

## Installation

* Download the latest version of the [PKS CLI](https://network.pivotal.io/products/pivotal-container-service)

### Oh-My-Zsh

* Clone this repo to your zsh plugins directory:

```
$ cd ~/.oh-my-zsh/plugins
$ git clone https://github.com/tybritten/pks-zsh-autocomplete-plugin.git pks
```

* Add the `pks` plugin to your `.zshrc` file:

```
plugins=(... pks)