# bearded-octo-batman

An experimental Vagrant setup for docker based development

To see how using something like this for docker-based development on my mac
works.

It's meant to work in the following way:

```
parent_dir -----> bearded-octo-batman
             |
             ---> code  -----> Vagrantfile
                          |
                          ---> project 1
                          |
                          ---> project 2
                          ..
```

The idea is that the `code` is where the vagrant instance is 'rooted',
such that all the projects in the code direcory can share it to use
a common development environment with a shared docker image repository.

## Setup

```sh
cd bearded-octo-batman
./script/setup
```

This creates the code directory, creates a link to this project's Vagrantfile
in it and provisions vagrant. It also links the `vagrunt` command into `~/bin`.

The setup script will have to be run twice to complete the install.

## Use

run the `vagrunt` command from inside a project directory to ssh into the
same directory inside the vagrant instance.
