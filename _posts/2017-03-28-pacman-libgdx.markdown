---
layout: post
title:  "Pacman"
date:   2017-03-28 22:36:07 +0200
categories: jekyll update
permalink: /pacman-libgdx
recap: Une implémentation de Pacman en Java avec LibGDX.
---

Pacman avec LibGDX
------------------

Lors d'un cours de Développement Mobile en troisième année de Licence
Informatique j'ai eu l'occasion de développer un jeu Pacman en Java en
utilisant la bibliothèque LibGDX.

![Pacman]({{ site.baseurl }}/assets/img/pacman/pacman.png)

Ce projet m'a permis de m'habituer un peu plus à l'utilisation de Java.

Il a fallu réfléchir à une bonne hiérarchie et organisation de classes
pour permettre une implémentation efficace et flexible.

Gestion des textures
====================

Pour la gestion des textures, une classe `TextureFactory` est utilisée.
Celle-ci contient une `Map` associant une classe à un objet 
`ITexturable`.

ITexturable est une interface déclarant une méthode `getTexture()`.

Ensuite on a créer différent wrapper pour encapsuler les éléments qui
ont besoin de plusieurs textures, par exemple les fantômes ou le pacman.

Ces wrapper ainsi que la `TextureFactory` sont munis d'une méthode
`update` permettant, selon le temps écoulé, de mettre à jour la texture
qui va être renvoyé par le wrapper.

Toute la logique pour déterminer quelle texture renvoyer est donc dans
les wrapper et la `TextureFactory` se contente d'appeler la méthode
`getTexture()` de l' `ITexturable`.

Gestion des IA des fantômes
===========================

Chaque fantôme possède une IA principale différente. Chaque IA est une
classe héritant de `GhostAI`.

Chaque fantôme possède 3 IA différentes, une pour sortir de la maison,
une utilisée par défaut (pour chasser pacman) et une dernière utilisée
lorsqu'ils sont effrayés.

Liens
=====

Vous pouvez accéder au code source de ce projet sur
[Github](https://github.com/Yutsa/Pacman-libgdx) ou bien
[Gitlab](https://gitlab.com/Yutsa/pacman).

Un `jar` exécutable contenant le jeu est disponible
[ici](
https://mega.nz/#!W8oRES6a!De3bKbgupTIvSLUSLWVSnMikILIPtchJv8yo5pbkvyo
)