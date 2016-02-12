# Vagrant Windows Development Environment

This Vagrantfile creates a windows vm for use in java Development

## Usage
Provision the system

`vagrant up`

RDP into the system

`vagrant rdp`

* Note: this requires rdp to be installed.

# Installed Software

* chocolatey package manager
* oracle jdk 8
* maven
* git
* posh-git
* intellij community edition

## Specs
```
memory = 4Gb
cpu = 2

User = IEUser
Password = Passw0rd!

Shared Folders

# maven settings will be copied to the $HOME\.m2
~/.m2 -> C:\shares\.m2
# ssh keys will be copied to $HOME\.ssh
~/.ssh -> C:\shares\.ssh
```

### Other Details

There are some powershell aliases for some easier command Usage

```
Maven
  mvn - aliased to mvn.cmd -Dmaven.repo.local=C:\shares\.m2\repository
  mqb - Quickbuild: mvn.cmd clean install '-D-Dmaven.repo.local=C:\shares\.m2\repository' -T 2C -Dfindbugs.skip=true -DskipTests=true -Dpmd.skip=true -Djacoco.skip=true -DskipTestScope=true -DskipProvidedScope=true -DskipRuntimeScope=true -P!documentation
Git
  gs: git status
  ga: git add
  gco: git checkout
  gb: git branch
  gd: git diff
```
