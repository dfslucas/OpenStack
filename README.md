# OpenStack
Configuração do Openstack no CentOs 7 em ambiente virtual

### Intallation PackStack

#### 1. Parar e desabilitar serviço de Firewall e NetworkManager:
```sh
$ systemctl disable firewalld NetworkManager
$ systemctl stop firewalld NetworkManager
```
#### 2. Habilitar e iniciar o serviço de Rede
```sh
# systemctl start network
# systemctl enable network
```
#### 3.	Desabilitar o Selinux
```sh
# setenforce 0
```
ou
```sh
# nano /etc/selinux/config
# Set SELINUX=disabled
```
### 4.	Configurar ambiente
```sh
# nano /etc/environment
```
LANG=en_US.utf-8 LC_ALL=en_US.utf-8

### 5.	Reboot
```sh
# reboot
```
### 6.	Instalar o pacote para habilitar o repositório do OpenStack:
```sh
# yum install -y centos-release-openstack-queens
```
### 7.	Update sync e reboot:
```sh
# yum -y update
# sync
# reboot
```
### 8.	Instalar o OpenStack-PackStack:
```sh
# yum install -y openstack-packstack
```
### 9.	Instalar utils do Openstack
```sh
# yum install openstack-utils
# yum install openstack-selinux
# yum install python-openstackclient
# openstack-status
```
### 11.	Criar answer file
```sh
# sudo packstack --gen-answer-file=~/answers.cfg
```
### 12. Configurar openstack
```sh
# nano answers.cfg
```
### 13. Start
```sh
# sudo packstack --answer-file=answers.cfg
```
### Config Network
