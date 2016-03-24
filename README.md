Instalação do Odoo
==================

Dependencias
============

    sudo apt-get -y install mercurial git python-software-properties libxslt1-dev python-virtualenv python-dev libpq-dev libsasl2-dev libldap2-dev python-libxml2 libxmlsec1-dev python-reportlab libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.5-dev tk8.5-dev python-tk libxml2-dev screen bzr

Java:
=====

    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java8-installer

Instalando o PostgreSQL
========================

    echo deb http://apt.postgresql.org/pub/repos/apt/ trusty-pgdg main | sudo tee /etc/apt/sources.list.d/postgresql.list
    wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
    sudo apt-get update
    sudo apt-get install postgresql-9.5 postgresql-contrib-9.5

Criando seu usuário no PostgreSQL
---

    sudo -i -u postgres createuser -U postgres --createdb --no-createrole --no-superuser $USER

Download do Pycharm
==================================

    sudo -i
    cd /tmp
    axel https://download.jetbrains.com/python/pycharm-community-5.0.4.tar.gz
    cd /opt
    sudo tar -zcvf /tmp/pycharm-community-5.0.4.tar.gz
    cd /usr/local/bin
    sudo ln -s /opt/pycharm-5.0.4/bin/pycharm.sh pycharm


Setup do Projeto
================================

 * Efetue o checkout deste repositório
 * No console, estando no diretório raiz do projeto, digite:
```
virtualenv .
bin/pip install --upgrade pip setuptools zc.buildout
```

 * Crie o seguinte diretório no seu "home" `~/.buildout/extends-cache`
 * Crie um arquivo chamado `~/.buildout/default.cfg` com o conteudo:
```
[buildout]
extengs-cache = /home/SEUUSER/.buildout/extends-cache
eggs-directory = eggs
download-cache = dlcache
```

 * Execute o buildout:
```
bin/buildout -N
```
 * Execute o odoo para testar:
```
bin/start_odoo
```
