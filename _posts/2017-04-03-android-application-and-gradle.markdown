---
layout: post
title:  "Application Android avec Gradle"
date:   2017-04-03 17:18:07 +0200
categories: jekyll update
permalink: /android-gradle
recap: Un exemple d'utilisation intermédiaire de Gradle pour Android
---

Présentation
============

J'ai récemment suivi un [cours](https://www.udacity.com/course/gradle-for-android-and-java--ud867) sur **Udacity** à propos de Gradle pour Android et Java.

Dans ce cours j'ai pu apprendre les bases de l'utilisation de Gradle dans des projets Java et Android. Je vais ici vous présenter le projet
final de ce cours.

Projet final
============

Le projet consistait à créer une application qui affichait une blague en appuyant sur un bouton. Cette application ne servant que de prétexte
à l'utilisation de Gradle pour gérer de plus gros projets Android, je me suis contenté de renvoyer un `String`, toujours la même.

Le coeur du projet était d'utiliser Gradle pour mieux organiser le projet.

### 1 - Création et utilisation d'une bibliothèque Java

La première étape était d'isoler le code permettant de récupérer une blague, et d'en faire une bibliothèque. J'ai donc créé un
module `jokegetter` pour y mettre le code qui sert à récupérer la blague. J'ai ensuite modifié le script Gradle pour ajouter cette nouvelle
bibliothèque à la liste des dépendances : `compile project(':jokegetter')`

### 2 - Création et utilisation d'une bibliothèque Android

Ensuite il fallait créer une bibliothèque Android pour isoler le code responsable de l'affichage de la blague. J'ai donc procédé de la même
manière que pour la bibliothèque Java.

À ce niveau du projet on a donc pu isoler la partie qui nous envoie la blague et la partie qui affiche la blague dans deux bibliothèques
que l'on a ajouté comme dépendances de notre application.

### 3 - Ajout d'un module "Google Cloud Endpoint"

Cette partie plus compliquée consistait à ajouter un module Google Cloud Endpoints. C'est à dire un serveur qui gérerait une API dans
le but d'obtenir les blagues. Notre application effectue donc une requête à cette API qui se charge d'appeler la bibliothèque Java
pour obtenir la blague à renvoyer.

Évidemment dans notre exemple ce n'est pas très utile, mais encore une fois l'application n'était qu'un prétexte pour étudier et
mettre en oeuvre ces technologies.

### 4 - Tests unitaires et Instrumented tests

Ensuite il fallait mettre en place une suite de tests unitaires mais également d'`instrumented tests`.

Les instrumented tests sont des tests s'exécutant sur l'appareil Android et permet donc de tester les parties du code
qui appellent l'API Android.

J'ai également utilisé la bibliothèque `Espresso` qui permet de tester les interactions avec l'UI de l'application.
C'est à dire simuler un clique sur un bouton etc.

### 5 - Version payante et version gratuite

Enfin la dernière partie consistait à mettre en place une version gratuite et payante de l'application. L'application
gratuite possède une bannière AdMob sur l'activité principale ainsi qu'une pub de transition entre le passage de
l'activité principale et de l'activité affichant la blague.

La version payante évidemment ne possède pas de pubs.

Les pubs sont obtenues par AdMob en utilisant Firebase, ce qui m'a permis de découvrir un petit peu cet outil également.

### Schéma final de l'application

![Schéma application]({{ site.baseurl }}/assets/img/gradle/recap.png)

Image credit to Udacity.

Conclusion
==========

Ce projet m'a permis d'approfondir mes connaissances en développement Android et dans la gestion de build en utilisant Gradle.

Vous pouvez retrouver le code sur [GitHub](https://github.com/Yutsa/udacity-BuildItBigger)
