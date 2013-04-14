---
layout: post
title: Conception et programmation d'un jeu web par l'exemple
category: personnel
tags:
- personnel
published: true
---

<h1 class="text-center">Conception et programmation d'un jeu web par l'exemple</h1>
<p class="muted text-center"><small>Article de <em>{{ page.content | number_of_words }} mots </em>publié par <em>Xavier</em> par un beau dimanche ensoleillé du <em>14 avril 2013</em> et qui vous prendra environ <em>xxx minutes</em> à lire. </small></p>
<hr>

## Qui

Je m'appelle Xavier, et je suis l'auteur de ce blog. Trentenaire, marié, père de famille, mon vrai boulot c'est la finance. Je ne suis pas programmeur, je n'ai jamais conçu de jeu, et je ne suis même pas ce qu'on pourrait appeler un gros *consommateur* de jeu (mais c'est surtout faite de temps).

Par contre, j'ai toujours adoré **créer**, et j'ai toujours un peu programmé depuis mon adolescence. Jamais rien de très sérieux, toutefois.

Mais depuis quelques mois, je me suis mis en tête d'essayer de créer un jeu web. Évidemment, entre le boulot, mes obligations familiales, le train train quotidien, et la fatigue générale, je suis continuellement en train de remettre le début du travail de conception et programmation au lendemain.

Mais il est temps de cesser de toujours reporter au lendemain. La vie est courte, le temps file, les semaines succèdent aux jours, et les années aux semaines, et j'ai le sentiment que si je ne m'y mets pas, je vais le regretter.

Donc, il est temps de commencer.

Cet article a pour objectif de vous parler de mon *projet de programmation d'un jeu web* et d'exposer brièvement la manière dont je vais m'y prendre et dont je rendrai compte de mes progrès. Si vous aussi vous avez un projet similaire dans vos cartons, vous devriez certainement vous reconnaitre dans les démarches et les difficultés que je décris.

## Quoi
Curieusement, même si je sais que je veux créer un jeu web, je n'ai pas encore décidé du type de jeu.

Des questions comme: Quel type de jeu? Dans quel univers de jeu? Quel mode de fonctionnement? resteront encore quelques temps sans réponse.

Par contre, je sais que je veux me lancer sur une **niche**. Pourquoi une niche? Parce-ce que, par définition, une niche est un domaine relativement épargnée par les gros studios, et donc sur lequel il y a moins de concurrent et où par conséquent j'ai une chance de pouvoir attirer des joueurs.

Mais trouver une niche va sans doute prendre du temps. Je veux passer un peu de temps à chercher avant de me lancer, afin de faire quelque chose qui soit, si possible, original.

Par ailleurs, une fois la niche déterminée, je compte lancer assez vite une version alpha, mal finalisée, bancale, mais à peu près jouable. Ceci afin de recueillir dès que possible un retour d'expérience des quelques joueurs qui auront bien voulu m'aider à tester le jeu, et prendre en compte ces retours pour améliorer le jeu.

L'alpha sera une suite d'itérations rapides, au fur et à mesure que j'intégrerai les retours d'expérience et les suggestions des joueurs, et que je corrigerai les bugs.

## Pourquoi

J'ai toujours été intéressé par la programmation, depuis tout petit. Ça a commencé sur mon [Commodore 64](http://fr.wikipedia.org/wiki/Commodore_64), à la fin des années 80, puis ça a continué sur PC.

Ah, comme j'avais rêvé de l'avoir, mon commodore, comme je l'avais voulu, voulu, voulu! Et j'ai fini par l'avoir :) Un vieux, d'occaze, avec le son qui ne marche pas. Mais une machine à moi, sur laquelle j'ai connu mes premiers émois de programmtion, en [Basic](http://en.wikipedia.org/wiki/Commodore_64#BASIC) bien sûr :)

Bon quelques années après je suis passé sur PC, et j'y suis resté fidèle jusqu'à aujourd'hui. Le PC m'a permis de découvrir d'autres langages de programmation, comme le turbo pascal, le c++, le PHP, et maintenant le Ruby avec Ruby on Rails. C'est la découverte de ce framework qui m'a donné envie de passer à la vitesse supérieure et de tenter la programmation d'un jeu.


## Comment

Et donc même si je n'ai pas encore d'idée arrêtée pour le jeu, j'ai toutefois déjà décidé d'une chose: il sera programmé avec [Ruby on rails](http://rubyonrails.org/).

Comme je m'intéresse à la programmation et que j'essaie de suivre de mon mieux l'évolution des langages de programmatin, je me suis tout naturellement intéressé aux [frameworks](http://fr.wikipedia.org/wiki/Framework) de développement web.

### Un framework

L'idée de ce blog n'est pas de faire un cours sur les frameworks, ni de les comparer pour déterminer le meilleur ou le plus rapide. Tout ce que je peux dire, c'est que je sens instinctivement qu'à l'heure actuelle essayer de développer un projet web relativement ambitieux en se passant d'un framework revient à réinventer la roue sur un grande partie du projet.

Donc il me semble indispensable de passer par un framework de développement. Après avoir jeté un rapide coup d'oeil sur quelques un, il m'a semble que Ruby on Rails était à la fois "fun", abordable, et permettait un développement vraiment rapide.

Comme je l'ai dit, je ne suis pas un programmeur professionnel. Mes connaissances en Ruby on Rails étaient de zéro il y a quelques semaines, et sont en train de s'améliorer petit à petit. Je ne suis pas encore capable de programmer un jeu, mais je vais quand même essayer :)

Je détaillerai dans un prochain article, et pour ceux que ça intéresse, le **plan d’apprentissage** de Ruby on Rails que je me suis élaboré après avoir consulté pas mal de sites et blogs sur le sujet.

### Un blog

Ce blog a pour objectif de présenter mon travail dans la conception d'un jeu, mettre par écrit mes idées, difficultés, succès ou échecs.

C'est un blog qui se veut *agréable à lire*, et dans cette phrase le mot clé est **lire**. J'ai fait quelques recherches sur la façon de présenter un texte en ligne pour qu'il soit le plus simple et agréable à lire. Je suis allé notamment sur les sites suivants (xxxxxxxxxxxxx).

Dès lors, j'utilise les caractéristiques suivantes.: taille des caractères et type, interligne, aération, paragraphes, sous titres, etc. Pas trop d'images.

Ceci sera amené à changer au gré de mes recherches, envies et sensibilités du moment.

Par ailleurs, je voulais un blog rapide. Après quelques recherches, j'ai finalement opté pour Jekyll, le tout hébergé sur Github, tout simplement. Site statique, Github, version control, édition partout, même au bureau. Tous les avantages presque sans inconvénient (quid de l'upload d'une image?)

Utilisation de [Markdown](http://daringfireball.net/projects/markdown/basics) et du sublime éditeur [Sublime Text](http://www.sublimetext.com/).

Je rédige donc le présent post dans Sublime Text, en mode "distraction free" (xxxx insérer capture d'écran)

![SideBlog - test image](/assets/images/5.png)

### Un mot sur les commentaires et le RSS

Ce blog se veut le plus simple possible. Et c'est très difficile. Tout comme pour la conception d'un jeu, la solution de facilité c'est d'avoir une usine à gaz dans laquelle on plug toutes les fonctionnalités possible et imaginables. Voyez ce qu'est devenu wordpress...

Mon objectif est donc de faire simple, d'aller à l'essentiel. Ais-je besoin dans l'immédiat d'un flux RSS? Et d'un système de commentaires des articles? Je ne le crois pas.

Néanmoins, que si vous souhaitez être prévenu de la publication de nouveaux articles, vous pouvez toujours vous abonner par email (voyez en pied de page).

## Où

Pas encore d'adresse pour le jeu, mais j'en parlerai sur ce blog.

## Quand

À déterminer.
