---
layout: post
title: Comment programmer Ruby on Rails sous Windows sans pleur ni douleur avec Vagrant
category: technique
published: true
---
<h1 class="text-center">Comment programmer Ruby on Rails sous Windows sans pleur ni douleur avec Vagrant</h1>
<p class="muted text-center"><small>Article de <em>{{ page.content | number_of_words }} mots </em>publié par <em>Xavier</em> par un frais dimanche du <em>28 avril 2013</em> et qui vous prendra environ <em>5 minutes</em> à lire. </small></p>
<hr>

J'ai un PC équipé de Windows 7, et je n’ai pas envie de changer. Je n’ai ni les moyens d’acheter un Mac (et, au passage, d'être pris pour un *pigeon* par Apple, ou une vache à lait), ni envie de configurer un dual boot pour installer linux sur le même PC.

Or, je ne pense pas lancer un gros troll en affirmant qu’en dehors de programmation .net, Windows est loi d’être l’outil de prédilection des programmeurs. Et il n’est certes pas idéal pour débuter avec Ruby on Rails.

Il est bien entendu tout à fait possible d'installer Ruby sous Windows. Mais on peut alors se retrouver limité par la suite, par exemple pour installer certaines "gems" qui doivent être compilées nativement sur le système sur lequel on les installe.

Par ailleurs, si comme moi votre objectif est de publier votre travail sur un serveur de production, il est plus logique d'essayer de développer sur un système le plus proche possible du serveur de production.

Alors, que faire pour programmer efficacement en Ruby on Rails, tout en restant sous Windows mais en évitant les limitations inhérentes à ce système?

## Oui, que faire ?

Eh bien ma solution (et celle de pas mal d’autres personnes, apparemment) s’appelle [Vagrant](http://www.vagrantup.com/).

Il s’agit d’un outil permettant de créer et distribuer des environnements de développements virtuels. Il permet ainsi de créer, par exemple sur un PC équipé de Windows, un environnement de développement virtuel sous, par exemple, Linux Ubuntu.

Vagrant permet en fait de créer un grand nombre d'environnements de développement différents. L'idéal est peut-être, en tous cas c'est mon choix, de répliquer l'environnement d'un serveur de production.

**Voici comment j’ai procédé :**

## 1. Installation de Ruby et Rubygems

Avant d’installer Vagrant, il faut installer Ruby et Rubygems. Comme je vous le disais, je suis sous Windows. À ce stade, je n'ai pas le choix: je dois télécharger une version Windows de Ruby pour pouvoir installer Vagrant et aller plus loi.

Pour ce faire, direction [RubyInstaller](http://rubyinstaller.org/), téléchargement de la dernière version, et installation. J'ai pour ma part installé la version 1.9.3p392.

Sur le même site, il faut également également télécharger le « development kit », et l’installer en suivant les indications données [ici](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit).

Je ne vous garanti pas que l'installation se passera bien... Les joies de Ruby sous Windows vous obligeront peut être (ce fut mon cas), à devoir traiter telle ou telle erreur obscure. Impossible d'entrer dans les détails ici, surtout que les erreurs possibles dépendent de votre configuation et de la version de RubyInstaller que vous avez téléchargée. Sachez que Google est votre ami et pourra très certainement vous aider si vous rencontrez une erreur. Par ailleurs, n'hésitez pas à éventuellement télécharger une version moins récente (à nouveau, ce fut mon cas).

En tous cas, sachez que c'est l'étape la plus difficile, donc ne vous découragez surtout pas.

Une fois cette petite prouesse accomplie, nous allons passer à l'installation de Vagrant.

## 2. Installation de Vagrant

Deuxième étape : j’installe Vagrant. Pour ce faire, rien de plus simple : j’invoque la ligne de commande Windows en tapant « cmd » dans la barre de recherche de programmes

![SideBlog - installation de Vagrant](/assets/images/1.png)

Ensuite, je tape simplement :

{% highlight ruby %}
gem install vagrant
{% endhighlight %}

![SideBlog - installation de Vagrant](/assets/images/2.png)

Et je laisse l’installation se faire gentillement.

Une fois l'installation de Vagrant achevée, nous allons voir comme installer le logiciel de virtualisation.

## 3. Installation de Virtualbox

Troisième étape, télécharger et installer [Virtualbox](https://www.virtualbox.org/). VirtualBox est un logiciel de virtualisation de systèmes d'exploitation. En utilisant les ressources matérielles de votre ordinateur, VirtualBox permet la création d'un ou de plusieurs ordinateurs virtuels dans lesquels s'installent d'autres systèmes d'exploitation.

Donc, VirtualBox va nous permettre de lancer effectivement notre environnement de développement sous Ubuntu.

Ah un détail au passage: si comme moi vous doutez de la fiabilité de ce genre de système, ou redoutez une éventuelle lenteur du système ainsi virtualisé, rassurez-vous. C'est fiable, et c'est suffisamment rapide pour faire du développement.

Passons maintenant à l'avant-dernière étape: l'installation du système d'exploitation sur notre ordinateur virtuel. Ceci se fait de manière relativement simple en installant une "box" Vagrant.

## 4. Installation d’une box Vagrant

Nous arrivons tout doucement au bout, avec le téléchargement et l’installation d’une « box » vagrant, c’est-à-dire d’un environnement de développement virtuel. En surfant sur [ce site](http://www.vagrantbox.es/) qui en présente un assortiement, mon choix se porte sur une version Ubuntu 11.10 server amd64.

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

et suivez les indications. En gros, le résultat de la commande va vous dire que, sous windows, vous ne pouvez pas vous connecter directement, et que vous allez devoir télécharger [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html), et le paramétrer avec les données qui sont affichées.

A noter qu’en ce qui me concerne, je n’ai pas pu utiliser la clé telle qu’elle était donnée. J’ai d’abord du la charger dans puttygen (fourni lors de l’installation de Putty), puis la sauvegarder à nouveau pour qu’elle soit utilisable par Putty (problème de format, apparemment).

Une fois connecté en SSH, il ne rest plus qu’à installer ruby on rails.

## 5. Installation de Ruby on Rails sur notre serveur virtuel

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

