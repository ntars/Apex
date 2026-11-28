[简体中文](README.md) | [English](README_EN.md) | [日本語](README_JA.md) | [한국어](README_KO.md) | **Français** | [Русский](README_RU.md) | [Español](README_ES.md) | [العربية](README_AR.md)

# Apex

**Le site officiel de Ntarstudio (星玖工作室) — et l'index des quinze projets.**

> **Ce dépôt a deux rôles** : il est la source du site du studio (un fichier HTML, une feuille de style, quelques scripts natifs) et il est **l'index des quinze projets**. Ce document porte sur le second : ce qu'est chaque projet, où il en est, où regarder. La mise en œuvre du site est comprimée au chapitre 5 et volontairement brève.

![Status](https://img.shields.io/badge/status-online-2ea44f?style=flat-square)
[![GitHub license](https://img.shields.io/github/license/ntars/Apex?style=flat-square)](./LICENSE)
[![GitHub Star](https://img.shields.io/github/stars/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/ntars/Apex?style=flat-square&color=3cb371)

[![Live](https://img.shields.io/badge/live-www.ntars.cn-0078d4.svg?style=flat-square)](https://www.ntars.cn/)
[![Projects](https://img.shields.io/badge/projects-15-8957e5.svg?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-none-2ea44f.svg?style=flat-square)](#)

---

## 1. Nom et positionnement

> **仓库描述 / Description**：`星玖工作室官网与十五个开源项目总索引：一个 HTML、一份样式表、几个原生脚本 | The Ntarstudio official site and an index of fifteen open-source projects, in one HTML file and a stylesheet.`
>
> **话题标签 / Topics**（20 个，仅英文）：`frontend`, `landing-page`, `no-framework`, `personal-website`, `portfolio-site`, `pwa`, `service-worker`, `single-page`, `static-site`, `studio-website`, `vanilla-css`, `vanilla-javascript`, `ntarstudio`, `chinese-website`, `html`, `css`, `javascript`, `dark-mode`, `responsive-design`, `no-dependencies`


**Nom** : Apex, « sommet ». En tant que site officiel du studio, il joue le rôle d'une entrée, non d'un produit.

**Positionnement en une ligne** : un site statique d'une seule page, sans dépendance ni build, qui énonce trois choses avec le minimum de code — qui c'est, ce qui est construit, où regarder.

**Trois limites** :

1. **C'est une plaque signalétique, pas une salle d'exposition.** Aucune fonctionnalité produit, aucune démo en ligne, aucune documentation intégrée. Les visiteurs poursuivent leur chemin via des liens directs vers chaque projet.
2. **Ce sont des fichiers statiques, pas une application.** Pas de backend, pas de base de données, pas de comptes. Tout le contenu est écrit dans `index.html` ; changer une ligne de texte, c'est un commit.
3. **C'est un index, pas une source de contenu.** L'information réelle d'un projet vit dans son propre dépôt et son propre site. Cette page résume et renvoie ; elle ne duplique pas.

**Pourquoi ce README met les projets au premier plan** : la section « 星玖工作室出品 » de la page d'accueil liste les quinze projets. Cette liste, le chapitre 3 de ce document et le README de profil GitHub sont trois rendus d'une même source. **Quiconque veut un aperçu rapide de ce que construit le studio n'a besoin que de cette page** — inutile d'ouvrir quinze dépôts.

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

## 3. Fonctionnalités clés

Le bloc « 星玖工作室出品 » de la page d'accueil présente quinze projets dans un seul ordre alphabétique latin ; chaque carte indique son propre état, et la formulation des états est définie en 3.2.

**Les quinze projets sont Amphoreus, Apex, Chiubay, Desop, Flutter-IDE, Gitrule-skill, NovaKit, Ondra, Relax, Serica, TapMC, Taycho-OS, Wacmin, Webroit et Xael.** GitHub les héberge et n'est pas un projet ; les quatre directions internes de Wacmin relèvent du détail d'implémentation et ne sont pas listées séparément.

### 3.1 Tous les projets (A–Z)

> Les quinze projets sont classés dans un seul ordre alphabétique latin, sans regroupement par état ; un nouveau projet est inséré à sa place, jamais ajouté à la fin. Cette liste, le tableau `PROJECTS` du site et le [profil ntars](https://github.com/ntars/ntars) restent identiques. La formulation des états est définie en 3.2.

#### Amphoreus · En développement

| | |
|---|---|
| Ce que c'est | Une reconstitution à l'identique du « Livre tel que je l'écris » d'Amphoreus, tiré de Honkai: Star Rail, transformée en monde simulé autonome : douze Titans, treize Héritiers dorés et douze braises calculés à partir d'une graine, la même graine donnant toujours la même histoire |
| Technique | Python 3.11+ (bibliothèque standard uniquement) · SQLite · HTML / CSS / Vanilla JS |
| État | En développement : le simulateur tourne et `/book` fonctionne ; les captures de référence officielles manquent, aucune correspondance au pixel près n'est revendiquée |
| Plateformes | macOS / Linux / Windows (bibliothèque standard uniquement) |
| Licence | MIT |
| Dépôt | <https://github.com/ntars/Amphoreus> |

La même graine donne toujours la même histoire ; une autre graine donne un autre Amphoreus. Le moteur de règles décide *ce qui s'est passé*, le modèle local seulement *comment le raconter*. À l'exécution, la page ne charge ni bitmap ni SVG : toutes les formes sont tracées avec des dégradés, des bordures et `clip-path`.

**Pourquoi le regarder** : il transforme « récit déterministe » et « interface sans image » en contraintes d'ingénierie vérifiables, et non en démonstration de concept.

#### Apex · En ligne

| | |
|---|---|
| Ce que c'est | Le site que vous lisez : l'enseigne du studio et l'index de tous les projets |
| Technique | HTML · CSS · Vanilla JS |
| Licence | MIT (règles dérivées d'asorn/asorn-open sous Apache-2.0, voir [LICENSING.md](LICENSING.md)) |
| Entrée | <https://www.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Apex> |

Un fichier HTML, une feuille de style, quelques scripts natifs. Pas de framework, pas de build, pas de backend. Zéro dépendance signifie qu'aucune chaîne d'outils ne pourra le casser plus tard.

**Pourquoi le regarder** : c'est un exemple de front-end sans build — comment un seul fichier HTML organise tout un site sans dépendre d'une chaîne d'outils vouée à disparaître.

#### Chiubay (玖白) · Prototype de recherche

| | |
|---|---|
| Ce que c'est | Faire grandir un agent depuis zéro sur le long terme : recherche personnelle sur les mécanismes de l'AGI, construite en six boucles de développement |
| Technique | Python · NumPy (tenseurs et rétropropagation écrits maison ; ni torch, ni JAX, ni poids pré-entraînés) |
| État | Prototype de recherche : la pile de tenseurs maison et l'expérience E3 sur l'identité fonctionnent ; les cinq autres boucles restent sur le papier |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Chiubay> |

L'objectif n'est pas de livrer une AGI de niveau humain, mais de décomposer « comment un agent est élevé jusqu'à prendre forme » en expériences de mécanismes réfutables. Chaque rapport n'énonce que ce qui a été vérifié, jamais que l'AGI est atteinte.

**Pourquoi le regarder** : il publie les règles d'entraînement, le protocole d'évaluation et les limites d'échec, et traite l'écart de puissance de calcul comme une limite physique, non comme un problème d'optimisation.

#### Desop · MVP constructible

| | |
|---|---|
| Ce que c'est | Une suite de bureau façon macOS pour Windows : dock, barre supérieure, widgets de bureau et îlot dynamique |
| Technique | Python 3.10+ · PySide6 (mode utilisateur) |
| Version | `0.2.0` |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Desop> |

Aucune modification du système, fonctionnement en mode utilisateur, et la désinstallation restaure le bureau. Les quatre composants partagent un jeu de jetons de design et s'activent séparément. Le budget de performance est un critère de publication : CPU au repos < 1 %, mémoire < 150 Mo, agrandissement du dock ≥ 55 fps ; s'il n'est pas tenu, pas de publication.

**Pourquoi le regarder** : il répond au reproche courant selon lequel les outils d'esthétique ralentissent la machine par des chiffres précis, et non par « nous optimiserons plus tard ».

#### Flutter-IDE · Disponible, 0.2.0

| | |
|---|---|
| Ce que c'est | Un IDE visuel Flutter centré sur le source : glisser des widgets sur un canevas, modifier les valeurs dans un panneau de propriétés et conserver du Dart maintenable sans l'outil |
| Technique | Dart 3.14+ · Flutter Desktop |
| Version | `0.2.0` |
| État | Disponible : validation et génération en CLI, arborescence et édition multi-onglets, glisser sur canevas, édition des propriétés, sélection par VM et hot reload, distribution macOS DMG/ZIP |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Flutter-IDE> |

Le seul critère qui décide de l'existence du projet : supprimez l'IDE, le projet doit toujours passer `flutter run`. Les contours d'intention, les surcouches et les jetons de design sont donc des fichiers texte versionnés dans git ; aucune structure de projet ne vit uniquement dans l'outil.

**Pourquoi le regarder** : « ne pas être enfermé dans un outil » y est écrit comme trois critères d'acceptation — pas de schéma privé, une modification donne un seul diff, la même entrée produit deux fois le même résultat — et non comme un slogan.

#### Gitrule-skill · Livré

| | |
|---|---|
| Ce que c'est | Un ensemble de spécifications couvrant tout le cycle de vie d'un projet : cadrage, exigences, architecture, développement, tests, déploiement, exploitation et itération, plus la documentation, la conformité et l'accès programmatique par les agents IA |
| Technique | Markdown (aucune dépendance tierce) · CLI Python · serveur MCP |
| Ampleur | 68 spécifications × 12 langues, avec les mêmes identifiants correspondant un à un dans chaque dossier de langue |
| État | Livré : la CLI ne signale aucun problème ; le Skill, le pack expert et le serveur MCP sont tous disponibles |
| Licence | MIT |
| Dépôt | <https://github.com/ntars/Gitrule-skill> |

Une spécification par fichier, indépendante et consultée à la demande. Une CLI sans dépendance vérifie les liens morts, les fichiers orphelins, les phrases de responsabilité, les blocs de code, les comptes d'index et l'enregistrement des espaces réservés ; `optimize` n'applique que les corrections sûres à automatiser.

**Pourquoi le regarder** : il transforme des conventions — les 20 chapitres d'un README, le nom d'un dépôt, la description et les topics — en fichiers et commandes vérifiables. L'alignement documentaire des quinze dépôts l'a pris pour unique référence.

#### NovaKit · Étape de squelette

| | |
|---|---|
| Ce que c'est | Les premiers outils à installer sur une machine neuve : fichiers, images, texte et petits utilitaires système dans une suite hors ligne, sans réseau ni compte |
| Technique | Rust (edition 2024) · Tauri 2 |
| État | Étape de squelette : le projet et la liste de 36 outils sont fixés, le code métier est en cours d'écriture, aucune version publiée |
| Plateformes | macOS d'abord ; Windows / Linux prévus |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/NovaKit> |

Les outils sont organisés en quatre niveaux — Rust pur, capacité système, composant externe, plugin de processus — chacun avec sa mise en œuvre et sa méthode d'acceptation. Les plugins parlent JSON-RPC 2.0 sur stdio, toutes les permissions étant refusées par défaut.

**Pourquoi le regarder** : il déduit la liste des outils de « ce dont on a besoin la première semaine après l'installation » et fixe la frontière de sécurité par niveau au lieu de gonfler en suite à tout faire.

#### Ondra (空谷) · Bêta interne, 3.0.0-alpha.22

| | |
|---|---|
| Ce que c'est | Un compagnon IA de bureau entièrement à plugins : l'interface ne lit que les projections des plugins ; émotion, mémoire et contexte sont les trois mécanismes centraux ; toutes les données restent sur la machine |
| Technique | Flutter (bureau et web) · Cordis 4.1.0 (cadre de plugins) · noyau dsh (Node) |
| Version | Bêta `3.0.0-alpha.22` |
| Plateformes | macOS fonctionne ; Windows dispose d'un paquet de publication ; le noyau Android démarre sur appareil (poignée de main réelle en attente) ; le web se compile ; iOS / OHOS n'ont que des projets générés |
| Licence | Apache-2.0 / MIT |
| Entrée | <https://ai.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Ondra> |

Trois mécanismes centraux : l'émotion (une variable d'état avec inertie), la mémoire (une chaîne à onze maillons) et le contexte (préfixe figé + injection incrémentale + emballage budgétaire). La page des plugins réunit 18 entrées embarquées et 75 de la couche d'assemblage, soit 93 entrées activables une à une.

**Pourquoi le regarder** : il décompose la compagnie en mécanismes isolément industrialisables, et un correctif d'ordre de démarrage a ramené de 55 à zéro les dégradations silencieuses de 18 plugins dues à des `apply` concurrents. Une seule couche de projection sépare l'interface des plugins, les pages ne détiennent jamais l'état interne d'un plugin.

#### Relax (悠然) · Développement précoce

| | |
|---|---|
| Ce que c'est | Une plateforme familiale auto-hébergée : discussion, agenda, fichiers et photos ; un seul serveur mono-processus, des clients Android, des données qui ne quittent pas la maison |
| Technique | Rust · Tauri 2 · axum · SQLite · React + TypeScript |
| État | Développement précoce : les squelettes de routes serveur (authentification, synchronisation, discussion, annonces, agenda, fichiers) sont en place ; la boucle métier n'est pas terminée |
| Plateformes | Serveur sous macOS / Linux ; client Android API 24+ |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Relax> |

Toute la logique métier vit en Rust : le front ne fait que rendre et appeler `invoke()` ; il n'émet aucune requête réseau, ne touche jamais SQLite directement et ne persiste aucun jeton. Les messages entrent dans une outbox et sont soumis de façon idempotente par `opId` après reprise.

**Pourquoi le regarder** : il transforme « la souveraineté des données » en cinq verrous architecturaux vérifiables par machine, et non en slogan de confidentialité.

#### Serica (行简) · Spécification gelée, implémentation arrêtée au lexer

| | |
|---|---|
| Ce que c'est | Un langage de programmation pour applications synchronisées multi-appareils : tout en chinois, sources `.serica`, commande `serica`, exécutables natifs en sortie |
| Technique | Go (compilateur d'amorce stage0) · voie d'auto-hébergement · écrit directement le Mach-O |
| Version | Spécification v3.1 gelée ; l'implémentation d'amorce s'arrête au lexer et à `check` : la génération d'IR (M3) et de code (M4) n'est pas implémentée, aucun exécutable ne peut encore être produit |
| Ampleur | 1 928 lignes d'amorce pour un plafond de 5 000, avec table d'attribution ligne par ligne ; le dossier d'amorce est supprimé après l'auto-hébergement |
| Licence | Apache-2.0 |
| Plateformes | Vérifié sur macOS arm64 uniquement |
| Dépôt | <https://github.com/ntars/Serica> |

Par conception, le compilateur d'amorce n'émet pas de C et n'appelle ni LLVM, ni assembleur, ni éditeur de liens : il écrit lui-même le Mach-O. La ponctuation chinoise relève de la grammaire au niveau lexical, pas de la typographie ; les diagnostics donnent la colonne en points de code et la colonne affichée (`ligne 3, colonne 38 (cellule 55)`). **Ce sont des objectifs de conception, pas les capacités actuelles** : seuls le lexer et la commande `check` fonctionnent ; `ir` renvoie « générateur d'IR non implémenté (M3) » et `build` « générateur de code non implémenté (M4) », donc aucun exécutable ne peut être produit et le langage **ne permet pas d'écrire un logiciel de production**.

**Pourquoi le regarder** : il fait de « le chinois n'est pas qu'une traduction de mots-clés » des contraintes vérifiables — plafond de 5 000 lignes, table d'attribution ligne par ligne, suppression de l'amorce après auto-hébergement, type de sortie qu'une seule commande `file` confirmera — plutôt qu'un document de pure vision.

#### TapMC · Étape de squelette, 0.1.0

| | |
|---|---|
| Ce que c'est | Un lanceur Minecraft Java Edition visant sept plateformes : instances, mods et runtimes Java gérés séparément, interface et couche de processus séparées par un seul contrat JSON-RPC |
| Technique | Flutter (interface) · Rust + eframe (enveloppe native) · Java 21 (côté serveur) |
| État | Étape de squelette : la chaîne fonctionne ; 84 tests Java et 21 cas Dart passent ; aucune version publiée |
| Plateformes | Web et Android compilent ; les cinq autres cibles ne sont pas vérifiées |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/TapMC> |

Le backend est l'unique source de vérité, le front ne fait que rendre et recueillir les entrées. Instances, mods et runtimes Java sont gérés séparément ; l'interface et l'enveloppe native partagent un seul contrat JSON-RPC. Le dépôt contient encore le code et les documents d'un ancien serveur bac à sable, à côté de la ligne du lanceur, sans nettoyage.

**Pourquoi le regarder** : il garde du côté interface la logique partagée par sept plateformes et confie la détection de Java et le contrôle des processus à l'enveloppe Rust, si bien que l'interface peut changer sans toucher à la gestion des processus. Les capacités inachevées (accès Modrinth, résolution des dépendances, versions Java multiples) sont listées une à une dans les limites connues au lieu d'être comptées comme faites.

#### Taycho-OS (太初) · Stade de conception (espace réservé)

| | |
|---|---|
| Ce que c'est | Un système natif écrit de zéro en Serica : modèle d'exécution, frontière de capacités, mécanisme de messages, fenêtres et texte, tous refaits |
| Technique | Serica (prévu) · exécutables natifs |
| État | Stade de conception : uniquement des documents de conception et un dépôt espace réservé ; aucun code |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Taycho-OS> |

Aucun noyau, runtime ou pile graphique existant n'est réutilisé ; chaque IO et chaque accès système doit déclarer une capacité, tout ce qui n'est pas déclaré est refusé.

**Pourquoi le regarder** : il énonce « de zéro » comme des conditions de frontière vérifiables par machine, et non comme un manifeste.

#### Wacmin · Disponible (trois directions livrables, AppOnWin expérimental)

| | |
|---|---|
| Ce que c'est | Une suite d'interopérabilité bidirectionnelle entre macOS et Windows, avec une couche d'accès pour l'IA |
| Technique | Node.js · Python · Rust |
| État | Trois directions livrables (Mac2Win / ExeOnMac / Win2Mac) ; AppOnWin est expérimental et non vérifié, l'environnement local ne le permettant pas |
| Licence | Apache-2.0 / MIT |
| Dépôt | <https://github.com/ntars/Wacmin> |

Quatre directions obtenues en croisant deux hôtes et deux actions ; les trois premières sont livrables, la quatrième reste expérimentale :

| Rang | Direction | Action sur l'hôte | Tests |
|---|---|---|---|
| 1 | **Mac2Win** | Produire un installeur Windows sur un Mac | 125 |
| 2 | **ExeOnMac** | Exécuter un programme Windows sur un Mac | 319 |
| 3 | **Win2Mac** | Produire un paquet d'application macOS sous Windows | 121 |
| 4 | **AppOnWin** | Exécuter un programme macOS sous Windows | Expérimental, non vérifié |

**Plus une couche d'accès `ai/`** : une même couche d'ordonnancement exposée en quatre formes — serveur MCP (pour Claude Desktop, WorkBuddy, Cline), CLI unifiée, Skill et pack expert. Les couches protocole et transport font ensemble moins de 900 lignes, sans dépendance tierce ; le SDK officiel n'a pas été utilisé.

**Pourquoi le regarder** : il ordonne le développement par certitude, laisse le maillon le plus susceptible d'échouer pour la fin et définit d'avance la voie de repli — même si la dernière direction échoue, les trois premières tiennent. Cette direction n'a pas produit de résultat de vérification reproductible : elle est donc marquée expérimentale et ne compte pas comme disponible. La couche `ai/` n'a pas été ajoutée comme un emballage MCP : elle est née de l'extraction de l'ordonnancement hors du shell vers `directions.mjs`, extraction qui a aussi révélé un défaut dormant — `/api/status` écrivait 21 lignes d'aide en chinois sur stdout à chaque requête et fixait `exitCode` à 2 ; la console ne le voyait pas puisqu'elle ne lit jamais son propre stdout, mais la règle MCP qui réserve stdout aux messages du protocole rend le procédé fatal.

#### Webroit · En ligne

| | |
|---|---|
| Ce que c'est | Une boîte à outils Android dans le navigateur : ADB et Fastboot en WebUSB, 61 fonctions implémentées et 152 prévues |
| Technique | TypeScript · Vite · WebUSB · ya-webadb |
| Forme | Site purement statique : sans backend, sans installation, sans pilote |
| Licence | Apache-2.0 / MIT |
| Entrée | <https://adb.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Webroit> |

Tout ce qu'il faut pour bricoler Android passe dans le navigateur. Le protocole ADB est implémenté au-dessus de Tango ; ce qui est livré, c'est l'interface et les parcours réellement utiles — gestion d'applications, navigation de fichiers, terminal, miroir d'écran, journaux et flashage — 61 implémentées et 152 prévues, chacune avec un niveau de risque.

**Pourquoi le regarder** : il supprime toute la couche « préparation de l'environnement ». Le chemin habituel est télécharger Platform-Tools → configurer PATH → installer un pilote USB → écrire des règles udev → connecter → taper des commandes ; Webroit compresse les cinq premières étapes en « ouvrir la page → cliquer connecter → cliquer une fonction ». La vraie difficulté n'a jamais été de taper des commandes, mais le moment où, après l'installation, l'appareil ne se connecte toujours pas et où l'on ne sait pas si c'est le câble, le port, le pilote ou un `adb.exe` qui tient encore l'interface.

**Deux points de plus** : tout le produit est un `dist/` statique, et `grep -r "http" dist/` n'y trouve aucune adresse de backend propre — « les données ne quittent pas cette machine » est un fait vérifiable, pas une promesse. Chaque opération est aussi classée par risque : une commande copiée ailleurs indique ce qu'elle va changer et si c'est réversible.

#### Xael (玄玖灵犀) · En ligne

| | |
|---|---|
| Ce que c'est | Un corpus local et hors ligne de calendriers chinois et de littérature divinatoire : 22 fonctions calculées de zéro, sans tables de correspondance ni réseau |
| Technique | JavaScript (zéro dépendance) · PWA · mini-programme WeChat · uni-app |
| Version | `5.0.0` |
| Licence | Apache-2.0 / MIT |
| Entrée | <https://x.ntars.cn/> |
| Dépôt | <https://github.com/ntars/Xael> |

Il couvre les Quatre Piliers, Zi Wei Dou Shu, Qi Men Dun Jia, Da Liu Ren, Liu Yao, Mei Hua Yi Shu, Xuan Kong Fei Xing et le choix des dates almanachiques. La base calendaire déduit les nouvelles lunes de séries astronomiques en temps réel au lieu de s'appuyer sur une table ; vingt classiques du domaine public servent de textes de référence, chaque règle étant corrigée article par article avec son niveau de preuve indiqué. Le mini-programme WeChat et le compte officiel sont cherchables sous le même nom.

**Pourquoi le regarder** : il mène jusqu'au bout le principe « calculer au lieu de chercher », et annote chaque conclusion avec sa base textuelle et ses points d'incertitude.

### 3.2 Formulation des états

**L'état du site et celui du produit ne sont pas équivalents** : un site qui tourne ne signifie pas un logiciel installable, et un logiciel qui tourne ne signifie pas un site accessible.

| Projet | État | Signification |
|---|---|---|
| Apex | En ligne | Le site tourne et la source est publique |
| Gitrule-skill | Livré | 68 spécifications × 12 langues, la CLI ne signale aucun problème ; pas de version publiée, livraison depuis la branche principale |
| Ondra | Bêta interne | `3.0.0-alpha.22` : macOS fonctionne, Windows a un paquet de publication, le noyau Android démarre sur appareil (poignée de main en attente), le web se compile |
| Wacmin | Disponible | Mac2Win / ExeOnMac / Win2Mac sont livrables, avec accès CLI et MCP ; AppOnWin est expérimental et ne compte pas comme disponible |
| Webroit | En ligne | Le site statique tourne sur `adb.ntars.cn`, 61 fonctions utilisables, source publique |
| Xael | En ligne | Une version stable (`5.0.0`) existe et est utilisable |
| Amphoreus | En développement | Simulateur et livre fonctionnent en local ; références officielles incomplètes, aucune revendication au pixel près |
| Flutter-IDE | Disponible | `0.2.0` : édition de bureau, glisser sur canevas, panneau de propriétés et distribution macOS utilisables |
| NovaKit | Étape de squelette | Le projet Tauri 2 et la liste de 36 outils sont en place ; le code métier n'a pas commencé |
| Chiubay | Prototype de recherche | La pile de tenseurs maison et l'expérience E3 fonctionnent ; les cinq autres boucles restent sur le papier |
| Taycho-OS | Stade de conception | Documents de conception et dépôt espace réservé uniquement ; aucun code |
| Relax | Développement précoce | Squelettes de routes serveur en place ; boucle métier inachevée ; pas d'APK |
| Serica | Spécification gelée | Spécification v3.1 gelée ; l'implémentation d'amorce s'arrête au lexer et au contrôle, génération d'IR et de code non implémentées ; aucune version, inutilisable pour un logiciel de production |
| TapMC | Étape de squelette | La chaîne fonctionne ; 84 tests Java et 21 cas Dart passent ; aucune version publiée |
| Desop | MVP constructible | `0.2.0` : l'implémentation Python + PySide6 en mode utilisateur se construit et s'exécute, 77 tests passent, acceptation sur VM Windows 11 8/8 PASS ; acceptation sur machine physique non faite; les widgets de bureau n'ont qu'une option de configuration, sans interface |

**Pourquoi les projets au stade de conception figurent quand même** : le site est l'enseigne du studio et montre ce qui se construit, pas seulement ce qui est terminé. Indiquer clairement l'état suffit : un visiteur qui lit « stade de conception » ou « étape de squelette » sait qu'il n'y a rien à télécharger, ce qui est plus honnête que de le cacher.

---

## 4. Caractéristiques clés

### Point fort 1 : quinze projets sur une page, trois sources synchronisées

- **Nom** : index unique.
- **Valeur** : résout « pour savoir ce que construit ce studio il faut ouvrir six dépôts ».
- **Mise en œuvre** : les cartes du site, le chapitre 3 de ce document et le README de profil GitHub listent le même ensemble avec le même libellé d'état.
- **Différenciation** : la plupart des pages personnelles ne listent que les projets publiés, ou dispersent l'information dans les README de chaque dépôt.
- **Preuve** : les trois listes correspondent élément par élément ; voir le tableau d'état en 3.2.

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

**`CACHE_NAME` vaut actuellement `ntarstudio-v12`.** Modifier quoi que ce soit dans la liste de pré-cache — y compris Typed.js chargé par CDN — impose d'incrémenter la version, sinon les visiteurs récurrents restent sur l'ancien cache.

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
6. **Les cartes des projets non publiés n'ont rien à télécharger** : le coût d'un libellé d'état honnête — et la raison pour laquelle rien de planifié n'est décrit comme construit.

---

## 16. Journal des modifications

Le journal vit sur la page **GitHub Releases** : <https://github.com/ntars/Apex/releases>

Le README décrit l'état actuel du site ; les releases enregistrent ce qui a changé à chaque fois. Les deux ne sont jamais mélangés.

---

## 17. Feuille de route

1. **Automatiser la version du cache** : remplacer le `CACHE_NAME` écrit à la main par un hachage d'actifs à la compilation.
2. **Icônes des cartes** : monter les icônes des quinze projets dès qu'elles existent ; toutes sont actuellement `icon: null`.
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