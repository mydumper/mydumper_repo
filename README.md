# MyDumper Repository

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
```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 79EA15C0E82E34BA
```
For ubuntu, the source file (/etc/apt/sources.list.d/mydumper.list) should be:
```
deb https://mydumper.github.io/mydumper/repo/apt/ubuntu ./
#deb https://mydumper.github.io/mydumper/repo/apt/ubuntu/testing ./
```
For debian, the source file (/etc/apt/sources.list.d/mydumper.list) should be:
```
deb https://mydumper.github.io/mydumper/repo/apt/debian ./
#deb https://mydumper.github.io/mydumper/repo/apt/debian/testing ./
```
