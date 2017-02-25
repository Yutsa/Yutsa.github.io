---
layout: post
title:  "PoGo-Spotted"
date:   2016-08-29 17:35:07 +0200
categories: jekyll update
permalink: /pogo-spotted
---

PoGo-Spotted
--------------

**PoGo-Spotted** est une application web utilisant le framework web
*Flask* ainsi que l'API JavaScript de Google Maps pour créer une carte
participative pour le jeu Pokemon Go.

![Menu]({{ site.url }}/assets/menu.png)

L'application permet dans un premier temps de rapporter les rencontres
que l'on fait avec des pokemon.

Par défaut l'application va tenter de géolocaliser l'utilisateur.

Si cela n'est pas possible, l'utilisateur pourra tout de même utiliser
une barre de recherche pour entrer l'adresse où il se trouve.

Ensuite il suffit de choisir le pokemon que l'on a croisé puis de 
changer la date si besoin.

![Rapporter un pokemon]({{ site.url }}/assets/report.png)

Les données envoyées sont stockées dans une base de données SQLite
pour être utiliser par la fonction `map`.

Dans la partie `map` on voit affiché sur une carte tous les pokemon qui ont été rapportés.

Plusieurs filtres sont disponibles pour cacher certains pokemon, ou
bien n'afficher que ceux qui ont été croisés dans un certains laps de
temps.

![Cartes]({{ site.url }}/assets/map.png)

Enfin la dernière fonctionnalité permet d'afficher le rayon de 200m
autour de sa position. Cela correspond à la porté de la liste des 
pokemon proches.

Cela veut dire que lorsqu'un pokemon est dans votre liste, il est 
forcément à l'intérieur de ce cercle.

![Pokemon Proche]({{ site.url }}/assets/nearby.png)

Il est également possible de créer de nouveaux cercles lorsque le 
pokemon n'est plus visible après avoir bougé.

En effet après s'être déplacé si le pokemon est trop loin et 
disparaît du radar cela veut dire qu'il n'est pas dans un rayon de 
200m. Le second cercle vous permettra donc d'éliminer des endroits
où le pokemon aurait pu apparaître.

![Second cercle]({{ site.url }}/assets/nearby2.png)

Ce projet est disponible sur [GitHub](https://github.com/Yutsa/PoGo-Spotted). Vous pouvez le modifier et le redistribuer.
