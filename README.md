# Instalação do ansible e docker

## 1. Configurações inicias para dar privilegios especificos no linux
##### Obs: user é o nome de usuráio do local host, ubuntu é a estação de trabalho.
#### Acesse o arquivo sudoers:  

>user@ubuntu:~$ sudo visudo

#### Localize *User privilege specification* embaixo e escreva o comando abaixo:

user  ALL=(ALL:ALL) NOPASSWD: ALL

## 2. Instalando o SSH:

>user@ubuntu:~$ sudo apt-get install openssh-server

#### Abra o arquivo do SSH:

>user@ubuntu:~$ sudo gedit etc/ssh/sshd_config

#### Altere o seguinte comando *#PermitRootLogin prohibit-password* para:

>PermitRootLogin yes

#### Reinicie o SSH server:

>user@ubuntu:~$ service ssh restart

#### Crie um chave SSH:

>user@ubuntu:~$ ssh-keygen

#### Faça copia da chave SSH:

>user@ubuntu:~$ cp -p ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys

## 3. Instalando o Ansible...

#### Crie um repositorio Ansible:

>user@ubuntu:~$ sudo apt-add-repository ppa:ansible/ansible

#### Confirme < ENTER >.

#### Faça uma atualização:

>user@ubuntu:~$ sudo apt-get update

#### Instale o Ansible:

>user@ubuntu:~$ sudo apt-get install ansible

#### Verifique a versão do Ansible:

>user@ubuntu:~$ ansible --version
