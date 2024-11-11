# MyDumper Repository
This repository is a submodule of MyDumper. The idea is to use a unique site https://mydumper.github.io/ to access all the info related to MyDumper.

## Yum
We need to import the GPG key:
```
wget -O GPG-KEY-MyDumper "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x79EA15C0E82E34BA"
rpm --import GPG-KEY-MyDumper
```
On /etc/yum.repos.d/mydumper.repo
```
[mydumper]
name=MyDumper
baseurl=https://mydumper.github.io/mydumper/repo/yum/
enabled=1
gpgcheck=1

[mydumper-testing]
name=MyDumper
baseurl=https://mydumper.github.io/mydumper/repo/yum/testing/
enabled=0
gpgcheck=1
```
## Apt
You need to import the key:
- For old versions
```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 79EA15C0E82E34BA
```
- Recommended
```
wget -qO- 'https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x1D357EA7D10C9320371BDD0279EA15C0E82E34BA&exact=on' | sudo tee /etc/apt/trusted.gpg.d/mydumper.asc
```
### Ubuntu
Source file (/etc/apt/sources.list.d/mydumper.list) should be:
```
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/ubuntu noble main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/ubuntu noble testing
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/ubuntu jammy main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/ubuntu jammy testing
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/ubuntu focal main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/ubuntu focal testing
```
### Debian
Source file (/etc/apt/sources.list.d/mydumper.list) should be:
```
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/debian bookworm main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/debian bookworm testing
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/debian bullseye main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/debian bullseye testing
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/debian buster main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/debian buster testing
```
### Ansible
```
deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} main
#deb [arch=amd64 signed-by=/etc/apt/keyrings/mydumper.asc] https://mydumper.github.io/mydumper/repo/apt/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} testing
```
