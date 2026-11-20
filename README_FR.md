[简体中文](README.md) | [English](README_EN.md) | [日本語](README_JA.md) | [한국어](README_KO.md) | **Français** | [Русский](README_RU.md) | [Español](README_ES.md) | [العربية](README_AR.md)

# Apex

**Le site officiel de Ntarstudio (星玖工作室) — et l'index des dix projets.**

> **Ce dépôt a deux rôles** : il est la source du site du studio (un fichier HTML, une feuille de style, quelques scripts natifs) et il est **l'index des dix projets**. Ce document porte sur le second : ce qu'est chaque projet, où il en est, où regarder. La mise en œuvre du site est comprimée au chapitre 5 et volontairement brève.

![Status](https://img.shields.io/badge/status-online-2ea44f?style=flat-square)
[![GitHub license](https://img.shields.io/github/license/ntars/Apex?style=flat-square)](./LICENSE)
[![GitHub Star](https://img.shields.io/github/stars/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/ntars/Apex?style=flat-square&color=3cb371)

[![Live](https://img.shields.io/badge/live-www.ntars.cn-0078d4.svg?style=flat-square)](https://www.ntars.cn/)
[![Projects](https://img.shields.io/badge/projects-9-8957e5.svg?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-none-2ea44f.svg?style=flat-square)](#)

---

## 1. Nom et positionnement

> **仓库描述 / Description**：`Apex —— 星玖工作室（Ntarstudio）官网与十个项目总索引：一个 HTML、一份样式表、几个原生脚本 | The Ntarstudio official site and an index of its ten projects: one HTML file, one stylesheet, a few plain scripts.`
>
> **话题标签 / Topics**（20 个，仅英文）：`frontend`, `landing-page`, `no-framework`, `personal-website`, `portfolio-site`, `pwa`, `service-worker`, `single-page`, `static-site`, `studio-website`, `vanilla-css`, `vanilla-javascript`, `ntarstudio`, `chinese-website`, `html`, `css`, `javascript`, `dark-mode`, `responsive-design`, `no-dependencies`


**Nom** : Apex, « sommet ». En tant que site officiel du studio, il joue le rôle d'une entrée, non d'un produit.

**Positionnement en une ligne** : un site statique d'une seule page, sans dépendance ni build, qui énonce trois choses avec le minimum de code — qui c'est, ce qui est construit, où regarder.

**Trois limites** :

1. **C'est une plaque signalétique, pas une salle d'exposition.** Aucune fonctionnalité produit, aucune démo en ligne, aucune documentation intégrée. Les visiteurs poursuivent leur chemin via des liens directs vers chaque projet.
2. **Ce sont des fichiers statiques, pas une application.** Pas de backend, pas de base de données, pas de comptes. Tout le contenu est écrit dans `index.html` ; changer une ligne de texte, c'est un commit.
3. **C'est un index, pas une source de contenu.** L'information réelle d'un projet vit dans son propre dépôt et son propre site. Cette page résume et renvoie ; elle ne duplique pas.

**Pourquoi ce README met les projets au premier plan** : la section « 星玖工作室出品 » de la page d'accueil liste les dix projets. Cette liste, le chapitre 3 de ce document et le README de profil GitHub sont trois rendus d'une même source. **Quiconque veut un aperçu rapide de ce que construit le studio n'a besoin que de cette page** — inutile d'ouvrir dix dépôts.

---

## 2. Présentation

### 2.1 Contexte

Les sites de studio échouent de deux façons. Soit ils deviennent des sites multi-pages pilotés par un CMS qui se figent en six mois et finissent plus anciens que les produits ; soit ils deviennent des portfolios démonstratifs où le premier écran est saturé d'animations, laissant les visiteurs incapables de trouver les liens vers les projets.

### 2.2 Problèmes traités

Un visiteur doit obtenir trois réponses dès l'arrivée : **qui c'est, ce qui est construit, où regarder**. Si la page met plus de trois secondes à répondre, elle a échoué.

### 2.3 Approche centrale

Le site a exactement trois responsabilités :

| Responsabilité | Approche |
|---|---|
| Établir l'identité de marque | Le premier écran relie 星玖工作室 / Ntarstudio / Ntars |
| Orienter vers l'open source | Six cartes menant directement aux adresses canoniques |
| Énoncer les faits honnêtement | Les informations non publiées ou retirées n'apparaissent jamais dans la page, les mots-clés ou les données structurées |

### 2.4 Cas d'usage

- La page signalétique officielle d'un petit studio indépendant ;
- Un site statique qui doit rester stable avec un entretien quasi nul ;
- Un exemple pédagogique de front-end sans build.

### 2.5 Non-objectifs

- Aucun compte, formulaire, cookie, outil d'analyse, publicité ni API backend ;
- Pas de jQuery / Vue / React / bibliothèque de composants UI, pas de Tailwind, pas de Vite / Webpack / Rollup ;
- Aucune écriture dans `localStorage` (la seule exception est traitée en 5.1 : l'état du thème n'est délibérément pas persisté).

---

## 3. Fonctionnalités clés : les dix projets

La section « 星玖工作室出品 » de la page d'accueil présente dix projets, classés par état : publiés d'abord, planifiés ensuite.

**Les dix projets sont Xael, Ondra, Webroit, Wacmin, Gitrule-skill, Apex, Flutter-IDE, TapMC, Serica et Desop.** GitHub est la plateforme qui les héberge, pas un projet ; les quatre directions internes à Wacmin sont un détail d'implémentation et ne sont pas listées séparément.

### 3.1 Publiés, livrés et en développement

#### Xael (玄玖灵犀) · Publié

| | |
|---|---|
| Ce que c'est | Corpus hors ligne de métaphysique chinoise : 22 fonctions calculées depuis les principes premiers, sans tables de correspondance, sans réseau |
| Technologies | JavaScript (aucune dépendance) · PWA · mini-programme WeChat · uni-app |
| Version | 5.0.0 |
| Licence | Apache-2.0 / MIT |
| Entrée | <https://x.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Xael> |

Couvre les Quatre Piliers, Zi Wei Dou Shu, Qi Men Dun Jia, Da Liu Ren, Liu Yao, Mei Hua Yi Shu, les Étoiles Volantes Xuan Kong et la sélection de dates du almanach. La base calendaire dérive les nouvelles lunes de séries astronomiques en temps réel plutôt que d'embarquer une table ; vingt classiques du domaine public servent de textes de référence, chaque règle étant corrigée élément par élément avec son niveau de preuve indiqué. Le mini-programme et le compte officiel sont recherchables sous le même nom.

**Pourquoi y jeter un œil** : il pousse « calculer plutôt que consulter » jusqu'au bout, et annote chaque conclusion avec sa base textuelle et l'incertitude restante.

#### Ondra (空谷) · Bêta interne

| | |
|---|---|
| Ce que c'est | Compagnon IA de bureau entièrement modulaire : l'interface ne lit que la projection des plugins ; émotion, mémoire et contexte sont les trois mécanismes clés ; les données restent locales |
| Technologies | Flutter (bureau et web) · Cordis 4.1.0 (framework de plugins) · noyau dsh (Node) |
| Version | `2.0.0-alpha` |
| Plateformes | macOS exécutable, web compilable ; les autres cibles n'ont que des projets générés |
| Licence | Apache-2.0 / MIT |
| Entrée | <https://ai.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Ondra> |

Trois mécanismes clés : émotion (état à inertie), mémoire (chaîne de onze maillons), contexte (préfixe figé + injection incrémentale + budget). La page des plugins fusionne 18 entrées embarquées et 75 entrées d'assemblage, soit 93.

**Pourquoi y jeter un œil** : l'accompagnement y est décomposé en mécanismes ingénierables séparément, et un correctif d'ordre de démarrage a ramené de 55 à 0 les dégradations silencieuses de 18 plugins.

#### Webroit · En ligne

| | |
|---|---|
| Ce que c'est | Une boîte à outils Android dans le navigateur : ADB et Fastboot en WebUSB, 152 fonctions |
| Technologies | TypeScript · Vite · WebUSB · ya-webadb |
| Forme | Site purement statique — sans backend, sans installation, sans pilotes |
| Licence | Apache-2.0 / MIT |
| Entrée | <https://adb.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Webroit> |

Tout ce qu'il faut pour bricoler un Android, ramené dans le navigateur. Le protocole ADB repose sur Tango ; ce qui est livré, c'est l'interface et les parcours qu'un utilisateur emploie vraiment — gestion d'applications, navigation de fichiers, terminal, miroir d'écran, journaux et flashage, 152 fonctions au total, chacune assortie d'un niveau de risque.

**Pourquoi y jeter un œil** : il supprime entièrement la couche « préparation de l'environnement ». Le parcours classique est télécharger Platform-Tools → configurer le PATH → installer les pilotes USB → écrire des règles udev → connecter → taper des commandes ; il compresse les cinq premières étapes en « ouvrir la page → cliquer sur connecter → cliquer sur une fonction ». Et la vraie difficulté n'a jamais été de taper les commandes, mais ce moment où, l'installation terminée, ça ne se connecte toujours pas et où l'on ne sait pas si c'est le câble, le port, le pilote, ou un `adb.exe` resté en arrière-plan qui tient l'interface.

**Deux points à retenir** : le produit est un `dist/` statique, et `grep -r "http" dist/` ne trouve aucune adresse de backend propre — « les données ne quittent pas votre machine » est un fait vérifiable, pas une promesse. Il classe aussi chaque opération par risque : une commande copiée quelque part indique ce qu'elle va changer et si c'est réversible.

#### Wacmin · Disponible

| | |
|---|---|
| Ce que c'est | Suite d'interopérabilité bidirectionnelle entre macOS et Windows |
| Technologies | Node.js · Python · Rust |
| Licence | MIT |
| Dépôt | <https://github.com/ntars/Wacmin> |

Remplit quatre directions en croisant « hôte » et « action » : produire un installeur Windows sur Mac, exécuter un programme Windows sur Mac, produire un bundle macOS sur Windows, exécuter un programme mac sur Windows. Les quatre partagent une couche de contrat avec des codes de sortie et des segments d'erreur unifiés.

**Pourquoi y jeter un œil** : il ordonne le développement par certitude, laisse l'échec le plus probable pour la fin et définit à l'avance un chemin de dégradation — même en cas d'échec, les trois premiers tiennent.

#### Gitrule-skill · Livré

| | |
|---|---|
| Ce que c'est | Un jeu de spécifications génériques couvrant tout le cycle de vie : cadrage, exigences, architecture, développement, tests, déploiement, exploitation, itération, ainsi que documentation, conformité et accès programmatique par IA |
| Technologies | Markdown (aucune dépendance tierce) · CLI Python · serveur MCP |
| Volume | 66 spécifications en chinois simplifié et en anglais, en correspondance un à un |
| État | Livré : le CLI ne signale aucun problème ; Skill, paquet expert et serveur MCP sont disponibles |
| Licence | MIT |
| Dépôt | <https://github.com/ntars/Gitrule-skill> |

Une spécification par fichier, indépendante et consultée à la demande. Un CLI sans dépendance vérifie les liens morts, les fichiers orphelins, les phrases de responsabilité, les blocs de code, les comptes d'index et l'enregistrement des espaces réservés.

**Pourquoi y jeter un œil** : les conventions — les 20 chapitres d'un README, le nom d'un dépôt, la rédaction de la description et des topics — deviennent des fichiers et des commandes vérifiables. L'alignement des dix dépôts s'est appuyé sur cette base unique.

#### Apex · En ligne

| | |
|---|---|
| Ce que c'est | Le site que vous lisez — la plaque du studio et l'index des projets |
| Technologies | HTML · CSS · Vanilla JS |
| Licence | MIT (Apache-2.0 pour les parties dérivées) |
| Entrée | <https://www.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Apex> |

Un fichier HTML, une feuille de style, quelques scripts natifs. Pas de framework, pas de build, pas de backend. Zéro dépendance signifie qu'il fonctionnera encore dans trois ans.

**Pourquoi y jeter un œil** : c'est un exemple de front-end sans build — comment un seul fichier HTML organise tout un site, et survit six ans sans mise à jour.

#### Flutter-IDE · Étape de squelette

| | |
|---|---|
| Ce que c'est | Un IDE visuel Flutter centré sur le source : glisser sur un canevas, modifier dans les panneaux, et produire du Dart maintenable sans l'outil |
| Technologies | Dart 3.14+ · Flutter Desktop |
| Version | `0.1.0` |
| État | Squelette : espace de travail, 47 jetons de design, protocole de blocs et cinq règles de validation terminés ; codegen, écriture AST et sélection restent à faire |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Flutter-IDE> |

Le seul critère d'existence du projet : supprimez l'IDE, le projet doit toujours passer `flutter run`. Les plans d'intention, les surcouches et les jetons de design sont donc des fichiers texte versionnés ; aucune structure ne vit uniquement dans l'outil.

**Pourquoi y jeter un œil** : « ne pas être prisonnier d'un outil » y est écrit comme trois critères d'acceptation — pas de Schema privé, une modification donne un seul diff, la même entrée produit deux fois le même résultat — et non comme un slogan.

#### TapMC · Étape de squelette

| | |
|---|---|
| Ce que c'est | Squelette de jeu sandbox multijoueur modulaire : un front Flutter sur sept cibles et un serveur Java, reliés par un seul contrat JSON-RPC 2.0 |
| Technologies | Flutter (front) · Java 21 (serveur) |
| État | Squelette : le chemin fonctionne, 61 tests serveur et 18 tests front passent ; aucune version publiée |
| Plateformes | Web et Android compilent ; les cinq autres cibles restent à vérifier |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/TapMC> |

Le serveur est l'unique source de vérité ; le front se contente d'afficher et de capter les entrées. Monde en grille 24×16, cinq types de blocs. Les mods ne reçoivent que `ModContext`, jamais `WorldGrid` : les règles ne peuvent pas être contournées.

**Pourquoi y jeter un œil** : la question « où les règles sont-elles calculées » est fixée par une contrainte de compilation, pas par la discipline en revue. Le noyau n'a aucune dépendance réseau, donc toute la logique se teste sans ouvrir de port (22 cas).

#### Serica（行简）· Étape de squelette

| | |
|---|---|
| Ce que c'est | Un langage de programmation pour applications synchronisées multi-appareils : tout en chinois, sources `.serica`, commande `serica`, exécutables natifs en sortie |
| Technologies | Go (compilateur germe stage0) · voie de l'auto-hébergement · écrit directement le Mach-O |
| Version | Étape `P1b` pre-alpha ; P0b a passé l'acceptation stricte sur macOS arm64 le 2026-11-20 |
| Taille | 1 928 lignes de germe pour un plafond de 5 000, avec table d'attribution ligne par ligne ; le répertoire germe est supprimé après l'auto-hébergement |
| Licence | Apache-2.0 (noyau et germe) / MIT (spécifications et écosystème) |
| Plateformes | Vérifié sur macOS arm64 uniquement, le reste non testé |
| Dépôt | <https://github.com/ntars/Serica> |

Le compilateur germe ne produit pas de C et n'appelle ni LLVM, ni assembleur, ni éditeur de liens : il écrit le Mach-O lui-même. La ponctuation chinoise est une grammaire au niveau lexical, pas de la typographie ; les diagnostics donnent à la fois la colonne en points de code et la colonne affichée (`ligne 3, colonne 38 (affichage 55)`), et reconstruire la même source donne des octets identiques. Ce qui fonctionne aujourd'hui : constantes de compilation, tranches en points de code, arithmétique entière, opérations bit à bit, tableaux constants et une fenêtre déclarative — **insuffisant pour écrire un logiciel de production**.

**Pourquoi cela vaut le détour** : « le chinois n'est pas qu'une traduction de mots-clés » y devient des contraintes d'ingénierie vérifiables — plafond de 5 000 lignes, table d'attribution ligne par ligne, suppression du germe après auto-hébergement, et un type de sortie qu'une seule commande `file` confirme.

### 3.2 Planifiés

**Le projet ci-dessous n'a que de la documentation — aucun code exécutable.** Le libellé d'état sépare strictement « publié » et « planifié ».


#### Desop · Planifié

| | |
|---|---|
| Ce que c'est | Suite de personnalisation du bureau Windows : dock, barre de menus, widgets, îlot dynamique |
| Technologies | À définir |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Desop> |

Aucune modification système, mode utilisateur pur, la désinstallation restaure tout. Les quatre composants partagent un jeu de jetons de design et peuvent être activés séparément. Le budget de performance est un seuil de publication : CPU au repos < 1 %, mémoire < 150 Mo, magnification du dock ≥ 55 fps — en dessous, pas de publication.

**Pourquoi y jeter un œil** : il répond à la plainte courante selon laquelle les outils de personnalisation ralentissent la machine par des chiffres précis, non par « nous optimiserons plus tard ».

### 3.3 Libellé d'état

**L'état du site et l'état du produit ne sont pas équivalents** — un site qui tourne ne signifie pas un logiciel installable, et un logiciel qui tourne ne signifie pas un site accessible.

| Projet | État | Signification |
|---|---|---|
| Xael | Publié | Une version stable existe, téléchargeable et utilisable |
| Ondra | Bêta interne | `2.0.0-alpha` : macOS exécutable, web compilable ; les autres cibles ne sont que générées |
| Webroit | En ligne | Site statique en service sur adb.ntars.cn, 26 fonctions utilisables, source publique |
| Wacmin | Disponible | Les quatre directions terminées et testées, avec accès CLI et MCP |
| Gitrule-skill | Livré | 66 spécifications en chinois et en anglais, CLI sans problème ; pas de numéro de version, livré depuis la branche main |
| Apex | En ligne | Le site tourne et la source est publique |
| Flutter-IDE | Étape de squelette | Contrats, jetons et cinq règles de validation utilisables ; codegen, écriture AST et sélection non implémentés ; aucune version publiée |
| TapMC | Étape de squelette | Le chemin fonctionne et 79 tests passent, sans version publiée |
| Serica | Étape de squelette | Le compilateur germe transforme le sous-ensemble P0b/P1b en Mach-O, et P0b a passé l'acceptation sur macOS arm64 ; aucune version publiée, inutilisable pour un logiciel de production |
| Desop | Planifié | Documentation seulement, aucun code exécutable |

**Pourquoi les projets planifiés figurent quand même sur le site** : le site est la plaque du studio, montrant « ce qui est en construction », pas seulement « ce qui est terminé ». Indiquer clairement l'état suffit — un visiteur qui lit « Planifié » sait qu'il n'y a rien à télécharger, ce qui est plus honnête que de le cacher.

---

## 4. Caractéristiques clés

### Point fort 1 : dix projets sur une page, trois sources synchronisées

- **Nom** : index unique.
- **Valeur** : résout « pour savoir ce que construit ce studio il faut ouvrir six dépôts ».
- **Mise en œuvre** : les cartes du site, le chapitre 3 de ce document et le README de profil GitHub listent le même ensemble avec le même libellé d'état.
- **Différenciation** : la plupart des pages personnelles ne listent que les projets publiés, ou dispersent l'information dans les README de chaque dépôt.
- **Preuve** : les trois listes correspondent élément par élément ; voir le tableau d'état en 5.9.

### Point fort 2 : zéro dépendance, zéro build, éditer et rafraîchir

- **Nom** : pas de chaîne d'outils.
- **Valeur** : résout « ça ne se build plus après six mois sans modification ».
- **Mise en œuvre** : pas de `node_modules`, pas de `package.json`, pas de fichier de verrouillage. `python3 -m http.server 8000` suffit pour prévisualiser.
- **Différenciation** : la plupart des « sites minimaux » utilisent encore Vite ou Webpack, au motif que « le modèle l'avait déjà ».
- **Preuve** : aucun `package.json` à la racine ; le déploiement est « push main → EdgeOne Pages publie automatiquement ».

### Point fort 3 : le thème suit le système, pas de flash blanc au premier rendu

- **Nom** : thème initial verrouillé sur deux images.
- **Valeur** : résout le flash blanc à l'ouverture sur un système sombre.
- **Mise en œuvre** : un script inline exécuté de façon synchrone dans `<head>` lit `prefers-color-scheme` et écrit le résultat dans `<html data-theme>` ; il ajoute d'abord `theme-lock` pour supprimer les transitions, puis le retire après deux images consécutives de `requestAnimationFrame` une fois le thème stabilisé.
- **Différenciation** : la pratique courante définit le thème sur `DOMContentLoaded`, ou ne fait rien pour éviter le flash.
- **Preuve** : une règle de transition unifiée de 0,5 s sous `html:not(.theme-lock)`.

### Point fort 4 : le halo des cartes suit le pointeur sans toucher au DOM

- **Nom** : halo piloté par variables CSS.
- **Valeur** : résout « les effets de survol provoquent des reflows ».
- **Mise en œuvre** : `app.min.js` calcule les coordonnées du pointeur relatives à la carte et les écrit dans `--mouse-x` / `--mouse-y` ; le `::before` de la carte peint le halo avec `radial-gradient`.
- **Différenciation** : l'approche courante déplace un élément positionné en absolu à chaque `mousemove`, forçant composition et reflow.
- **Preuve** : `app.min.js` ne fait que calculer des coordonnées et écrire des variables.

### Point fort 5 : les deux pièges de défilement des dialogues traités

- **Nom** : compensation de la barre de défilement et direction de sortie.
- **Valeur** : résout deux erreurs que presque tout dialogue fait maison commet — la page qui se décale à droite à l'ouverture, le panneau « aspiré » dans un coin à la fermeture.
- **Mise en œuvre** : à l'ouverture, ajouter `padding-right` avant `overflow: hidden` ; à la fermeture, attendre la fin de la transition d'`opacity` (avec un minuteur de secours de 500 ms) avant de restaurer le défilement, en ne transitionnant que `opacity` et jamais `transform`.
- **Différenciation** : toucher à `transform` déplace le panneau vers l'origine de transformation, ce qui donne l'impression qu'il est aimanté.
- **Preuve** : sous `prefers-reduced-motion`, l'animation est ignorée et le minuteur de 500 ms est le seul chemin qui ferme encore le dialogue.

---

## 5. Détails de conception et arbitrages techniques

**C'est le seul chapitre consacré au site lui-même.** Il est volontairement comprimé — les projets sont l'essentiel.

### 5.1 Thème : suit le système, surchargeable manuellement, non mémorisé

Un double-clic sur « 星玖工作室出品 » inverse le thème manuellement et synchronise `<meta name="theme-color">` pour que la barre d'adresse mobile suive.

**L'état manuel n'est délibérément pas écrit dans `localStorage`.** L'expérience par défaut suit le système ; chaque interrupteur stocké est un état de plus à expliquer. Un rechargement revient à la préférence système.

### 5.2 Cinq blocs de page

De haut en bas : salutation, séparateur, projets, entrée « contact » en haut à droite, pied de page. Plus quatre calques persistants (canvas de feux d'artifice, canvas de traînée, canvas de particules d'arrière-plan, décoration basse).

Pas de routeur, pas de DOM virtuel ; le défilement est natif.

### 5.3 Trois bandes d'appareils dans la salutation

| Appareil | Détection | Affichage |
|---|---|---|
| Téléphone | Fenêtre < 768 px | Hi, I'm **Ntars** |
| Tablette | 768–1180 px avec tactile | Mode studio en paysage, mode personnel en portrait |
| Bureau | Le reste | Hi, We're **Ntarstudio** |

La détection de tablette exige en plus `ontouchstart in window` ou `navigator.maxTouchPoints > 0`, sinon une grande fenêtre de navigateur serait mal détectée.

### 5.4 Cartes de projet : pilotées par configuration

Les cartes sont rendues depuis le tableau `PROJECTS`, chaque entrée portant titre, description, lien et icône optionnelle. `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))` avec un écart de 16 px donne trois colonnes sur bureau et une sur écran étroit, sans media query.

Changer l'état d'un projet, c'est changer une ligne de données, pas un bloc de HTML — ce qui évite « j'ai changé la carte mais oublié les métadonnées » et « les cartes ont divergé structurellement ».

### 5.5 Six scripts plutôt qu'un

| Fichier | Responsabilité |
|---|---|
| `security.js` | Désactive sélection/copie/clic droit/raccourcis ; détection de falsification |
| `app.min.js` | Halo des cartes : coordonnées du pointeur → variables CSS |
| `anime.js` | anime.js v2.0.2 (tiers, MIT, non modifié) |
| `firework.js` | Particules de feux d'artifice |
| `trail.js` | Traînée du pointeur |
| `bg.js` | Particules d'arrière-plan et liens |

Chaque fichier fait une chose et peut être retiré seul. La seule dépendance dure est `firework.js` envers `anime.js`, d'où l'ordre fixe : `security → app.min → anime → firework → trail → bg`.

### 5.6 Le numéro de version du cache est l'étape la plus facile à oublier

**`CACHE_NAME` vaut actuellement `ntarstudio-v9`.** Modifier quoi que ce soit dans la liste de pré-cache — y compris Typed.js chargé par CDN — impose d'incrémenter la version, sinon les visiteurs récurrents restent sur l'ancien cache.

### 5.7 Les limites honnêtes des mesures de sécurité

`security.js` intercepte la sélection, la copie, le couper, le clic droit, le glisser, F12 et les raccourcis d'affichage du code source.

**Pour être clair : ces mesures ne font qu'élever le seuil de la copie occasionnelle ; elles n'apportent aucune protection du contenu.** Le code front-end est toujours visible par les visiteurs, et aucun script n'y change rien.

### 5.8 Liste blanche CSP

| Directive | Valeur |
|---|---|
| `default-src` / `script-src` | `'self'`, inline, `https://unpkg.com` |
| `img-src` | `'self'` et `data:` |
| `frame-src` / `object-src` | `'none'` |
| `connect-src` | `'self'` (aucune requête API externe) |

Plus `nosniff`, `X-Frame-Options: DENY` et `referrer: no-referrer`.

### 5.9 La discipline des trois emplacements

Lorsqu'un état de projet change (publication, retrait, changement de domaine), ces trois éléments doivent être mis à jour ensemble :

1. Le tableau `PROJECTS` dans `index.html` ;
2. Le chapitre 3 de ce document ;
3. Le tableau des projets du README de profil GitHub `ntars/ntars`.

**Les projets retirés ne reviennent sous aucune forme** — ni dans la page, ni dans les mots-clés, ni dans les données structurées.

---

## 6. Pile technique et dépendances

### 6.1 Pile

| Couche | Choix |
|---|---|
| Structure | HTML5 natif, balises sémantiques plus complément `role` |
| Style | CSS natif : propriétés personnalisées + Grid + Flexbox |
| Interaction | JavaScript natif (syntaxe surtout ES5) |
| Animation | anime.js v2.0.2, uniquement pour les particules de feux d'artifice |
| Polices | Pile de polices système ; aucune police web |
| Hors ligne | Service Worker + Web App Manifest |
| Déploiement | EdgeOne Pages |

### 6.2 Composants tiers

| Composant | Version | Ayant droit | Licence | Intégration | Usage |
|---|---|---|---|---|---|
| asorn/asorn-open | — | asorn | Apache-2.0 | Dérivation de source | Base initiale |
| anime.js | v2.0.2 | Julian Garnier (2017) | MIT | Fichier entier embarqué | Chronologie et easing des feux d'artifice |
| Typed.js | 2.0.16 | Matt Boldt | MIT | CDN unpkg + pré-cache SW | Effet de frappe de la salutation |

**Dérivation** : ce projet modifie, étend et redessine l'interface et la structure à partir de asorn/asorn-open, ce qui en fait une œuvre dérivée. Conformément à la clause 4 d'Apache-2.0, la mention de copyright d'origine, le texte intégral de la licence et une déclaration de modifications sont conservés.

### 6.3 Explicitement non utilisés

Polices web tierces · bibliothèques d'icônes tierces · frameworks front-end et bibliothèques UI · analyse et suivi · publicité et widgets de commentaires/support · cookies et écritures en stockage local · API backend et bases de données.

### 6.4 Dépendances indirectes

Aucune. Il n'existe pas de dépendance transitive.

---

## 7. Installation et déploiement

```bash
python3 -m http.server 8000
# ouvrir http://localhost:8000
```

Pas d'étape de build ; modifier puis rafraîchir. Le Service Worker ne s'enregistre que sur `localhost` ou en HTTPS — `file://` n'est pas pris en charge.

**Il n'existe qu'un seul chemin de déploiement** : push `main` → EdgeOne Pages publie automatiquement, avec `www.ntars.cn` pointant vers le site. Le dépôt ne contient aucun fichier de workflow.

---

## 8. Démarrage rapide

### 8.1 Pour découvrir les projets

Lisez le chapitre 3 ci-dessus, ou visitez <https://www.ntars.cn/>.

### 8.2 Pour exécuter le site en local

1. `git clone https://github.com/ntars/Apex.git`
2. `cd Apex && python3 -m http.server 8000`
3. Ouvrir `http://localhost:8000`
4. Double-cliquer « 星玖工作室出品 » pour vérifier le changement de thème
5. Réduire la fenêtre sous 768 px pour vérifier le texte en mode téléphone
6. Cliquer sur « Contact » en haut à droite pour vérifier le dialogue

---

## 9. Configuration

Il n'y a pas de fichier de configuration. Tout ce qui est ajustable tient en trois endroits :

| Contenu | Emplacement | Quoi changer |
|---|---|---|
| Cartes de projet | le tableau `PROJECTS` dans `index.html` | Titre, description, lien, icône optionnelle |
| Couleurs du thème | `:root` et `[data-theme="dark"]` dans `assets/css/base.css` | Propriétés CSS personnalisées |
| Version du cache | `CACHE_NAME` dans `sw.js` | À incrémenter dès qu'un actif pré-caché change |

---

## 10. API et modules

Il n'y a pas d'API. Les responsabilités des scripts sont en 5.5. L'ordre de chargement est fixe : `security → app.min → anime → firework → trail → bg`.

---

## 11. Arborescence

```
Apex/
├── index.html                 # Structure + métadonnées + quatre scripts inline
├── manifest.json              # Manifeste PWA
├── sw.js                      # Service Worker
├── LICENSE                    # Texte intégral MIT
├── LICENSE-Apache-2.0.txt     # Texte intégral Apache-2.0 (parties dérivées d'asorn)
├── NOTICE                     # Mentions de copyright et de tiers
├── README.md / README_EN.md
└── assets/
    ├── css/
    │   ├── base.css           # La seule feuille de style chargée
    │   ├── base.scss          # Source de style correspondant à base.css
    │   └── base.min.css       # Version minifiée
    ├── js/
    │   ├── security.js
    │   ├── app.min.js
    │   ├── anime.js           # Tiers, MIT
    │   ├── firework.js
    │   ├── trail.js
    │   └── bg.js
    └── img/                   # Mot-symbole N+T maison et icônes PWA
```

---

## 12. Performance

| Métrique | Valeur | Notes |
|---|---|---|
| Étapes de build | 0 | Ni bundling ni minification |
| Requêtes externes au premier écran | 1 | Typed.js (CDN unpkg, pré-caché) |
| Polices web | 0 | Pile de polices système |
| Reflows | 0 | Le halo n'écrit que des variables CSS |
| Visites répétées | Servi depuis le cache | Service Worker, cache d'abord |

---

## 13. Sécurité et confidentialité

| Dimension | Approche |
|---|---|
| Cookies | Non utilisés |
| Stockage local | Aucune écriture (l'état manuel du thème n'est délibérément pas persisté) |
| Analyse | Aucune |
| Requêtes tierces | Typed.js uniquement (CDN unpkg) |
| CSP | Liste blanche déclarée ; `object-src` / `frame-src` à `'none'` |
| Clickjacking | `X-Frame-Options: DENY` |
| Fuite de référent | `referrer: no-referrer` |

**Une note honnête sur la protection du contenu front-end** : `security.js` ne fait qu'élever le seuil de la copie occasionnelle et n'apporte aucune protection.

---

## 14. Compatibilité

| Environnement | État | Notes |
|---|---|---|
| Navigateurs modernes | ✅ Complet | Propriétés CSS personnalisées natives + Grid |
| Navigateurs anciens | ⚠️ Dégradé | Les scripts sont surtout ES5 ; le thème ne s'applique pas mais le contenu reste lisible |
| Téléphone (< 768 px) | ✅ | Une colonne pleine largeur |
| Tablette (768–1180 px tactile) | ✅ | Double mode selon l'orientation |
| Bureau (≥ 1180 px) | ✅ | Cartes sur trois colonnes |
| Ouvert via `file://` | ⚠️ Partiel | Le Service Worker ne s'enregistre pas ; le reste fonctionne |

---

## 15. Problèmes connus et limites

1. **La version du cache dépend d'un humain** : oublier d'incrémenter `CACHE_NAME` laisse les visiteurs récurrents sur un ancien cache, sans qu'aucune erreur ne soit levée.
2. **L'état manuel du thème n'est pas persisté** : un rechargement revient à la préférence système — par conception.
3. **Le basculement au tap est désactivé sur tablette** : le mode suit l'orientation.
4. **La protection du contenu front-end ne fonctionne pas** : `security.js` ne fait qu'élever le seuil.
5. **Typed.js vient d'un CDN** : si unpkg est injoignable, l'effet de frappe échoue, le reste du contenu n'est pas affecté.
6. **Les cartes des projets planifiés n'ont rien à télécharger** : le coût d'un libellé d'état honnête — et la raison pour laquelle rien de planifié n'est décrit comme construit.

---

## 16. Journal des modifications

Le journal vit sur la page **GitHub Releases** : <https://github.com/ntars/Apex/releases>

Le README décrit l'état actuel du site ; les releases enregistrent ce qui a changé à chaque fois. Les deux ne sont jamais mélangés.

---

## 17. Feuille de route

1. **Automatiser la version du cache** : remplacer le `CACHE_NAME` écrit à la main par un hachage d'actifs à la compilation.
2. **Icônes des cartes** : monter les icônes des dix projets dès qu'elles existent ; toutes sont actuellement `icon: null`.
3. **Audit d'accessibilité** : `role`, `tabindex` et `aria-*` sont présents, mais un parcours clavier complet et un test de lecteur d'écran n'ont pas été faits.
4. **Réduire les dépendances tierces** : Typed.js est assez simple pour être remplacé par une quarantaine de lignes natives.
5. **Image d'aperçu Open Graph** : il n'y a actuellement pas d'`og:image`.

---

## 18. Contribution

### 18.1 Auto-vérification avant modification

1. Les titres, descriptions et liens des six cartes correspondent à l'état réel des projets ;
2. `description`, `keywords`, `og:*`, JSON-LD et `canonical` restent synchronisés avec le corps du texte ;
3. Si un actif pré-caché a changé, `CACHE_NAME` a été incrémenté ;
4. Les thèmes clair et sombre ont été vérifiés ;
5. Aucune troncature ni débordement aux largeurs téléphone, tablette et bureau ;
6. L'arrière-plan ne défile pas pendant que le dialogue est ouvert, et la position ne saute pas après fermeture ;
7. **Un changement d'état se fait à trois endroits** (tableau `PROJECTS`, chapitre 3 de ce document, README de profil GitHub).

### 18.2 Discipline de publication

- Vérifier `CACHE_NAME` après chaque changement de contenu ;
- Lorsqu'un état de projet change, mettre à jour ensemble la carte, les métadonnées et le tableau d'état ;
- Les projets retirés ne doivent jamais revenir dans la page, les mots-clés ou les données structurées ;
- Confirmer la compatibilité de licence avant d'ajouter un composant tiers, et l'enregistrer dans `NOTICE` avant de committer.

### 18.3 Contact

| Canal | Adresse |
|---|---|
| Site | <https://www.ntars.cn/> |
| GitHub | <https://github.com/ntars> |
| README de profil | <https://github.com/ntars/ntars> |
| Courriel | <ntars@qq.com> · <ntarsx@163.com> |

---

## 19. Copyright et licence

| Portée | Licence |
|---|---|
| Code original (structure, styles, scripts et modifications ultérieures) | MIT, voir [`LICENSE`](LICENSE) |
| Parties dérivées de asorn/asorn-open | Apache-2.0, voir [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| Noms de marque, logo, design de l'interface | Tous droits réservés, voir [`NOTICE`](NOTICE) |

La redistribution doit conserver `NOTICE`, `LICENSE`, `LICENSE-Apache-2.0.txt` et les mentions de copyright et de licence dans l'en-tête de `assets/js/anime.js`.

**Noms et marques.** Les noms et marques 「星玖工作室」, 「Ntarstudio」, 「玄玖灵犀」, 「Xael」, 「NT-Xhex」, 「空谷」, 「Ondra」, 「Wacmin」, 「TapMC」, 「Desop」, 「行简」 et 「Serica」 appartiennent à Ntarstudio. MIT et Apache-2.0 n'accordent que des droits d'auteur, pas de droits de marque.

Copyright (c) 2024–2026 星玖工作室 Ntarstudio

---

## 20. NOTICE — Conformité open source

Chaque composant et actif tiers utilisé par ce projet est divulgué élément par élément dans [NOTICE](NOTICE).

| Composant | Intégration | Licence | Modification |
|---|---|---|---|
| asorn/asorn-open | Dérivation de source | Apache-2.0 | Modifié (interface et structure redessinées) |
| anime.js v2.0.2 | Fichier entier embarqué | MIT | Non modifié |
| Typed.js 2.0.16 | CDN unpkg | MIT | Non modifié |

**Les obligations de la clause 4 d'Apache-2.0 sont remplies** : la mention de copyright d'origine, le texte intégral de la licence et une déclaration de modifications sont conservés.

**Procédure d'ajout d'un composant tiers** : confirmer la compatibilité de licence avec le MIT / Apache-2.0 de ce projet → l'enregistrer dans `NOTICE` (nom, version, ayant droit, licence, adresse, usage, modification) → puis committer. Lorsqu'une licence ne peut être confirmée, la marquer « non confirmée » et suspendre la fusion.

---

Ntarstudio · <https://www.ntars.cn/>