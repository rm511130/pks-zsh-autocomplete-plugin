# [PKS](https://pivotal.io/platform/pivotal-container-service) CLI zsh autocomplete plugin

We use the [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) custom plugin framework for [zsh](http://www.zsh.org/) [autocompletion](https://github.com/zsh-users/zsh-completions/blob/master/zsh-completions-howto.org) to enhance the PKS CLI experience with options for all its PKS commands.

# How will it work?

When, for example, you type `pks c` and then press `Tab` you will be offered the following choices to autocomplete your command:

```
cluster                 -- View the details of the cluster
clusters                -- Show all clusters created with PKS
create-cluster          -- Creates a kubernetes cluster, requires cluster na
create-network-profile  -- Create a network profile
create-sink             -- Creates a sink for sending all log data to syslog
```

Let's say you picked the `create-cluster` option and that you typed in the name `k8s-cluster`.

You should have `pks create-cluster k8s-cluster`. You then press `Tab` again to see additional choices:

```
--external-hostname  -- Address from which to access Kubernetes API
--help               -- help for create-cluster
--json               -- Return the PKS-API output as json
--network-profile    -- Optional, network profile name (NSX-T only)
--non-interactive    -- Dont ask for user input
--num-nodes          -- Number of worker nodes
--plan               -- Preconfigured plans. Run pks plans for more details
--wait               -- Wait for the operation to finish
```

If you select `--plan` and then press `Tab` again, you will be given a choice of plans created by your Ops Team. For example:

```
large   medium  small 
```

You can continue to press `Tab` for additional choices until you are satisfied with the complete command line at which point you will press `return` to execute the command.


## Installation

* Download the latest version of the [PKS CLI](https://network.pivotal.io/products/pivotal-container-service)

* On a Mac, you'll need you will need to execute the following command to install the [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) framework: 

```sh -c "$(curl -fsSL https://tinyurl.com/install-oh-my-zsh-MacOS)"```

* For other Operating Systems look for the oh-my-zsh framework installation instructions [here](https://github.com/robbyrussell/oh-my-zsh)


### Let's extend the Oh-My-Zsh framework with a custom PKS plugin:

* Clone this repo to your zsh custom plugins directory:

```
cd ~/.oh-my-zsh/custom/plugins
git clone https://github.com/rm511130/pks-zsh-autocomplete-plugin.git pks
```

* Add the `pks` plugin to your `~/.zshrc` file:

```
plugins=(... pks ...)
```

In my case, as an example, that part of the `~/.zshrc` file looks like this:

```
# Which plugins would you like to load?
# Standard plugins can be found in ~/.oh-my-zsh/plugins/*
# Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.

plugins=(git pks kubectl cloudfoundry)

source $ZSH/oh-my-zsh.sh
```

As you can see, the `pks` custom plugin has been added to the list.

* Additionally, in order to enable the oh-my-zsh autocompletion, append the following lines at the end of the same `~/.zshrc` file:

```
# enable autocomplete function
autoload -Uz compinit
compinit
```

### Next Steps

* Make sure you start a new terminal window so that the changes described above take effect.

* Double check that you are using `zsh`

```
echo $SHELL
/bin/zsh
```

* Try typing `pks` and then press the `Tab` key. You should see the following list of choices:

```
cluster                 -- View the details of the cluster
clusters                -- Show all clusters created with PKS
create-cluster          -- Creates a kubernetes cluster, requires cluster na
create-network-profile  -- Create a network profile
create-sink             -- Creates a sink for sending all log data to syslog
delete-cluster          -- Deletes a kubernetes cluster, requires cluster na
delete-network-profile  -- Delete a network profile
delete-sink             -- Deletes a sink from the given cluster
get-credentials         -- Allows you to connect to a cluster and use kubect
get-kubeconfig          -- Allows you to get kubeconfig for your username
help                    -- Help about any command
login                   -- Log in to PKS
logout                  -- Log out of PKS
network-profile         -- View a network profile
network-profiles        -- Show all network profiles created with PKS
plans                   -- View the preconfigured plans available
resize                  -- Changes the number of worker nodes for a cluster
sinks                   -- List sinks for the given cluster
update-cluster          -- Updates the configuration of a specific kubernete
upgrade-cluster         -- Upgrades the kubernetes clusters
```
