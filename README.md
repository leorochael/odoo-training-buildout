Instalação do Odoo
=======================
Dependencias
sudo apt-get -y install mercurial git python-software-properties libxml2 libxslt1-dev python-setuptools python-dev libpq-dev libsasl2-dev libldap2-dev python-libxml2 libxmlsec1-dev python-reportlab libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.5-dev tk8.5-dev python-tk libxml2-dev screen bzr

Java:
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer

PostgreSQL
========================
1 - 
sudo apt-get install postgresql-9.5 ou inferior
sudo apt-get install postgresql-contrib-9.5
2- CRIANDO UM USUÁRIO PARA O POSTGRES
sudo su -
su - postgres
createuser --createdb --username postgres --no-createrole --no-superuser --pwprompt treinamento

Instalando o pip
==========================================
cd /tmp
wget https://bootstrap.pypa.io/get-pip.py
sudo python get-pip.py

Download do Pycharm
==================================
cd /tmp
axel https://download.jetbrains.com/python/pycharm-community-5.0.4.tar.gz
cd /usr/lib
sudo tar -zcvf /tmp/pycharm-community-5.0.4.tar.gz
cd /var/bin/
sudo ln -s /usr/lib/pycharm-5.0.4/bin/pycharm.sh pycharm


SETUP PROJETO
================================
1 - Abra o pycharm com ctrl + F2 e efetue o checkout do repositório do buildout
2 - Abrir o projeto
3 - No console digitar: virutalenv .
4 - Baixar o buildout padrão em https://github.com/odoo-brazil/odoo-brazil-buildout na wiki
5 - Corrigir o extends c/ https://raw.githubusercontent.com/odoo-brazil/odoo-brazil-buildout/oca/default.cfg
6 - Crie um arquivo chamado no seu home:
	nano ~/.buildout/default.cfg

	Com o conteudo:

[buildout]
eggs-directory = /home/SEUUSER/.buildout/eggs
download-cache = /home/SEUUSER/.buildout/dlcache

7 - Instale o reportlab manualmente
	bin/pip install reportlab==2.7
8 - Movendo o executavel python
mv bin/python bin/python.old
nano bin/buildout e altere o nome do arquivo python na primeira linha 
( Tenho que ver o pq disso, geralmente não uso virutalenv)

8 - Execute o buildout:
	bin/buildout
9 - Execute o odoo para testar.

=D 
