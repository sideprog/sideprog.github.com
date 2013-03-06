---
layout: post
title: Comment programmer Ruby on Rails sous Windows sans pleur ni douleur
category: technique
published: true
---
<h2 class="text-center">Comment programmer Ruby on Rails sous Windows sans pleur ni douleur</h2>
<p class="muted text-center"><small>Ecrit par <em>Xavier</em> par un beau dimanche ensoleillé du <em>25 février 2013.</em> </small></p>
---
Je suis sous Windows 7, et je n’ai pas envie de changer. Je n’ai ni les moyens d’acheter un Mac, ni envie de configurer un dual boot pour y installer linux.

Or, je ne pense pas lancer un gros troll en affirmant qu’en dehors de programmation .net, Windows est loi d’être l’outil de prédilection des programmeurs. Et il n’est certes pas idéal pour débuter avec Ruby on Rails.
Comment faire alors ?

### Et Vagrant entra dans pièce

Eh bien ma solution (et celle de pas mal d’autres personnes, apparemment) s’appelle Vagrant.

Il s’agit d’un outil permettant de créer et distribuer des environnements de développements virtuels. Il me permet ainsi de créer, sous mon petit Windows adoré, un environnement de développement virtuel sous, par exemple, Linux Ubuntu.

Voici comment j’ai procédé :

### 1. Installation de Ruby et Rubygems
Avant d’installer Vagrant, il faut installer Ruby et Rubygems. Pour ce faire, direction RubyInstaller, téléchargement de la dernière version, et installation. J’ai bien entendu pris la dernière version (Ruby 1.9.3-p125 au moment où j’écris ces lignes).

Sur le même site, il faut également également télécharger le « development kit », et l’installer en suivant les indications données ici.

### 2. Installation de Vagrant
Deuxième étape : j’installe Vagrant. Pour ce faire, rien de plus simple : j’invoque la ligne de commande Windows en tapant « cmd » dans la barre de recherche de programmes

![SideBlog - installation de Vagrant](/assets/images/1.png)

Ensuite, je tape simplement :

{% highlight ruby %}
gem install vagrant
{% endhighlight %}

![SideBlog - installation de Vagrant](/assets/images/2.png)

Et je laisse l’installation se faire gentillement.

### 3. Installation de Virtualbox

Troisième étape, télécharger et installer Virtualbox, qui va permettre de lancer effectivement notre environnement de développement. Au moment où j’écris ces lignes, c’est Virtualbox 4.1.8 qui est la dernière version pour Windows.

### 4. Installation d’une box Vagrant

Voici déjà la dernière étape : le téléchargement et l’installation d’une « box » vagrant, c’est-à-dire d’un environnement de développement virtuel. En surfant sur ce site qui en présente un assortiement, mon choix se porte sur une version Ubuntu 11.10 server amd64.

Elle s’installe de la façon suivante : retour dans la ligne de commande, et entrée des commandes :

{% highlight ruby %}
vagrant box add ubuntu-1110-server-amd64 http://timhuegdon.com/vagrant-boxes/ubuntu-11.10.box
vagrant init ubuntu-1110-server-amd64
vagrant up
{% endhighlight %}

Et voilà, la box est lancée. Il nous reste à nous connecter à notre serveur ubuntu tout neuf, via ssh. Pour ce faire, tapez

{% highlight ruby %}
vagrant ssh
{% endhighlight %}

et suivez les indications. En gros, le résultat de la commande va vous dire que, sous windows, vous ne pouvez pas vous connecter directement, et que vous allez devoir télécharger Putty, et le paramétrer avec les données qui vous sont données.

A noter qu’en ce qui me concerne, je n’ai pas pu utiliser la clé telle qu’elle était donnée. J’ai d’abord du la charger dans puttygen (fourni lors de l’installation de Putty), puis la sauvegarder à nouveau pour qu’elle soit utilisable par Putty (problème de format, apparemment).

Une fois connecté en SSH, il ne rest plus qu’à installer ruby on rails.

### 5. Installation de Ruby on Rails sur notre serveur virtuel

Je suis donc désormais connecté à mon serveur virtuel en SSH via Putty.
![SideBlog - installation de Vagrant](/assets/images/3.png)

L’installation de Ruby et Rails est alors assez facile. Il suffit d’entrer les commandes suivantes :

#### Mise à jour du système

{% highlight ruby %}
sudo apt-get update
sudo apt-get install build-essential zlib1g-dev git-core sqlite3 libsqlite3-dev curl libssl-dev libreadline6-dev postgresql postgresql-server-dev-9.1
{% endhighlight %}

#### Installation de rbenv

{% highlight text %}
cd
git clone git://github.com/sstephenson/rbenv.git .rbenv
echo export PATH= $HOME/.rbenv/bin:$PATH  >> ~/.bash_profile
echo eval $(rbenv init -)  >> ~/.bash_profile
source ~/.bash_profile

git clone https://github.com/sstephenson/ruby-build.git
cd ruby-build
sudo ./install.sh

rbenv install 1.9.2-p290
rbenv rehash
rbenv global 1.9.2-p290
ruby -v
{% endhighlight %}

#### Installation de Ruby on Rails

{% highlight ruby %}
gem install rails
gem install bundler
rbenv rehash
bundle
{% endhighlight %}

Et voilà!

Vous avez maintenant en environnement de développement Ruby on Rails parfaitement fonctionnel, sous Ubuntu, accessible directement depuis votre PC sous Windows :).

J’espère avoir été clair dans les explications. Si vous voyez des choses à ajouter/modifier ou si des points vous semblent nébuleux, n’hésitez pas à le signaler en commentaire afin que je mette ce petit tutoriel à jour.

