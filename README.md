# Servidor Lamp Digital Ocean

```
$ adduser admin
$ visudo
```

Alterar para: 
```
admin ALL=(ALL:ALL) ALL
```

Instalando Lamp:
```
$ sudo apt-get install tasksel
$ sudo tasksel
```

Instalando PhpMyAdmin:
```
$ sudo apt-get install phpmyadmin
```

Reiniciando o servidor:
```
$ sudo service apache2 restart
```

Instalando Proftpd:
```
$ sudo apt-get install proftpd
$ sudo nano /etc/proftpd/proftpd.conf
```

Alterar para:
```
DefaultRoot /var/www/
```

Adicionando permissão para usuário:
```
$ sudo adduser admin www-data
$ sudo chown -R www-data:www-data /var/www
$ sudo chmod -R g+rw /var/www
$ sudo service proftpd restart
```

Habilitando ModRewrite:
```
$ sudo a2enmod rewrite
```

Instalando Curl:
```
$ sudo apt-get install php5-curl
```

Alterando Time Zone:
```
$ sudo dpkg-reconfigure tzdata
```

Reiniciando o Cron:
```
$ /etc/init.d/cron stop
$ /etc/init.d/cron start
```

Configurando o Apache:
```
$ sudo nano /etc/apache2/sites-enabled/000-default.conf
```

Criar mapeamento de host:
```
<VirtualHost *:80>
  ServerName www.exemplo.com
  ServerAlias exemplo.com www.exemplo.com
  DocumentRoot /var/www/exemplo
</VirtualHost>
```

#NodeJS

## Instalando última versão do NPM

```
$ sudo npm install npm@latest -g
```

No windows, o npm vem junto com o NodeJs.

## Instalando a última versão do NodeJS

### Via Npm

```
$ sudo npm cache clean -f
$ sudo npm install -g n
$ sudo n stable
$ sudo ln -sf /usr/local/n/versions/node/<VERSION>/bin/node /usr/bin/node
$ sudo ln -sf /usr/local/n/versions/node/<VERSION>/bin/node /usr/bin/nodejs
```

### Nativo

```
$ curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
$ sudo apt-get install -y nodejs
```

# Alterando Motd

```bash
$ sudo nano /etc/motd
```

# Instalando sshpass no Mac OsX

https://gist.github.com/arunoda/7790979

```bash
brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb
```

# Ubuntu Themes

https://itsfoss.com/install-numix-ubuntu/

```bash
sudo add-apt-repository ppa:numix/ppa
sudo apt-get update
sudo apt-get install numix-gtk-theme numix-icon-theme-circle
sudo apt-get install numix-wallpaper-*
```

# Git

Savando a senha em cache:

```bash
$ git config --global credential.helper cache
```

Salvando a senha em definitivo:

```bash
$ git config --global credential.helper store
```

Setando tempo maior:

```bash
$ git config --global credential.helper "cache --timeout=3600"
```

Buffer:

```bash
$ git config --global http.postBuffer 1048576000
```

Realocando:


```bash
$ git remote set-url origin <new-url>
```

Forçando arquivos diferentes:

```
git fetch --all
git reset --hard origin/master
```
ou

```
git stash save --keep-index
```

Alias para add, commit e push

```
git config --global alias.cmp '!f() { git add -A && git commit -m "$@" && git push; }; f'
```

Git considerando o case:

```
git config core.ignorecase false
```

# ZSH

```bash
$ apt-get install zsh
$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Mac

http://sourabhbajaj.com/mac-setup/

## Change File Encoding

```bash
iconv -f iso-8859-1 -t utf-8 < file > file.new
```

## Plugins Para o Zsh

https://medium.com/@ivanaugustobd/seu-terminal-pode-ser-muito-muito-mais-produtivo-3159c8ef77b2

## Coisas Legais

https://medium.com/@Jarvski/customizing-the-os-x-terminal-11fda5c3dd5c

## New Line POWERLEVEL(k

https://github.com/bhilburn/powerlevel9k/wiki/Stylizing-Your-Prompt
