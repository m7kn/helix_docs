# Documentation de l'Éditeur Helix

## Introduction

Helix est un éditeur de texte moderne et modal. L'édition modale signifie que nous pouvons travailler avec le texte dans différents modes. Les deux modes principaux sont :

- Mode Normal : Les touches exécutent des commandes au lieu de taper des caractères
- Mode Insertion : Utilisé pour taper des caractères

## Mouvements de Base

Déplacement du curseur en mode Normal :

- `h` - gauche
- `j` - bas
- `k` - haut
- `l` - droite

## Quitter

- `:q` ou `:quit` - quitter (uniquement si pas de modifications non sauvegardées)
- `:q!` ou `:quit!` - quitter en abandonnant les modifications non sauvegardées
- `:wq` ou `:write-quit` - sauvegarder et quitter

## Suppression et Insertion

- `d` - supprimer le caractère sous le curseur
- `i` - entrer en mode Insertion avant le curseur
- `a` - entrer en mode Insertion après le curseur (append)
- `I` - entrer en mode Insertion au début de la ligne
- `A` - entrer en mode Insertion à la fin de la ligne
- `o` - insérer une nouvelle ligne en dessous et entrer en mode Insertion
- `O` - insérer une nouvelle ligne au-dessus et entrer en mode Insertion

## Sauvegarde

- `:w` ou `:write` - sauvegarder le fichier actuel
- Un nom de fichier/chemin optionnel peut être spécifié

## Mouvement et Sélection

- `w` - avancer au début du mot suivant
- `e` - avancer à la fin du mot actuel
- `b` - reculer au début du mot actuel
- `W`, `E`, `B` - comme les variantes minuscules mais s'arrêtent uniquement aux espaces

## Commandes de Modification

- `c` - supprimer le texte sélectionné et entrer en mode Insertion
- `d` - supprimer le texte sélectionné
- Nombre + commande : exécuter la commande plusieurs fois (ex: `2w`)

## Mode Sélection

- `v` - basculer le mode sélection
- `x` - sélectionner la ligne entière
- `;` - réduire la sélection au curseur

## Copier et Coller

- `y` - copier (yank) le texte sélectionné
- `p` - coller après le curseur
- `P` - coller avant le curseur
- `Space + y/p` - opérations avec le presse-papiers système

## Recherche

- `/` - rechercher vers l'avant
- `?` - rechercher vers l'arrière
- `n` - occurrence suivante
- `N` - occurrence précédente
- Supporte les expressions régulières

## Curseurs Multiples

- `C` - dupliquer le curseur à la ligne correspondante suivante
- `Alt-C` - dupliquer le curseur à la ligne correspondante précédente
- `s` - sélectionner les correspondances dans le texte sélectionné
- `&` - aligner les sélections

## Autres Fonctions

- `u` - annuler
- `U` - rétablir
- `.` - répéter la dernière insertion
- `~` - basculer la casse
- `` ` `` - convertir en minuscules
- `Alt-`` ` ``- convertir en majuscules
- `Ctrl-c` - commenter/décommenter la ligne

## Gestion des Fenêtres

- `Ctrl-w nv` - nouvelle division verticale
- `Ctrl-w ns` - nouvelle division horizontale
- `Ctrl-w h/j/k/l` - se déplacer entre les fenêtres
- `Ctrl-w q` - fermer la fenêtre actuelle
- `Ctrl-w o` - fermer toutes les autres fenêtres
- `:vs` / `:hs` - ouvrir une division avec un nom de fichier

## Mode Match

Le mode Match, activé avec la touche `m`, est utilisé pour gérer les parenthèses et autres caractères appariés :

- `mm` - sauter au caractère correspondant
- `mi(` - sélectionner le contenu entre parenthèses
- `ma(` - sélectionner les parenthèses et leur contenu
- `ms(` - entourer le texte sélectionné avec des parenthèses
- `md(` - supprimer les parenthèses entourantes
- `mr([` - remplacer les parenthèses par un type différent

D'autres caractères appariés peuvent être utilisés à la place des parenthèses, ex: `{}`, `[]`, `""`, `''`.

## Utilisation des Registres

Les registres sont des conteneurs identifiés par des caractères qui peuvent servir différents objectifs :
- Copier/couper du texte
- Stocker des expressions de recherche
- Stocker des macros

- `"<ch>` - sélectionner un registre (ex: `"a`)
- Sauvegarder dans le registre sélectionné avec la commande `y`
- Coller depuis le registre sélectionné avec `p` ou `P`

## Macros

Les macros sont des séquences de commandes qui peuvent être rejouées plus tard :

- `Q` - commencer l'enregistrement de macro (par défaut dans le registre `@`)
- `Q` - terminer l'enregistrement de macro
- `q` - jouer la macro depuis le registre `@`
- `"<ch>Q` - enregistrer une macro dans un registre spécifique
- `"<ch>q` - jouer une macro depuis un registre spécifique

## Recherche et Sélection

- `*` - rechercher le mot sous le curseur
- `n`/`N` en mode `v` - ajouter une nouvelle sélection à l'occurrence suivante/précédente
- `Ctrl-s` - sauvegarder la position dans la liste de sauts
- `Ctrl-i`/`Ctrl-o` - avancer/reculer dans la liste de sauts
- `gw` - afficher les étiquettes à deux caractères pour la navigation rapide

## Gestion des Sélections

- `)` / `(` - déplacer la sélection primaire en avant/arrière
- `Alt-,` - supprimer la sélection primaire
- `Alt-)` / `Alt-(` - échanger le contenu des sélections
- `S` - diviser les sélections basées sur un motif regex

## Manipulation de Lignes

- `J` - joindre les lignes sélectionnées
- `>` / `<` - augmenter/diminuer l'indentation
- `Ctrl-a` / `Ctrl-x` - incrémenter/décrémenter un nombre

## Gestion Avancée des Fenêtres

- `Ctrl-w t` - transposer la disposition des fenêtres
- `Ctrl-w H/J/K/L` - déplacer la fenêtre dans la direction donnée
- `Space f` - ouvrir le sélecteur de fichiers
  - `Ctrl-v` - ouvrir le fichier sélectionné dans une division verticale
  - `Ctrl-s` - ouvrir le fichier sélectionné dans une division horizontale

## Astuces et Conseils

1. La plupart des commandes peuvent être combinées :
   - Nombre + commande : exécution multiple
   - Registre + commande : opération avec un registre spécifique
   - Mouvement + opération : opération sur le texte sélectionné par le mouvement

2. Stratégies d'édition efficaces :
   - Utiliser la commande `.` pour les changements répétitifs
   - Curseurs multiples pour l'édition parallèle
   - Mode Match pour le traitement de texte structuré
   - Macros pour les séquences d'opérations complexes

3. Opération de recherche et remplacement :
   - Sélection dans la zone affectée
   - Commande `s` pour sélectionner les correspondances de motif
   - Commande `c` pour exécuter le changement

4. Modèles de gestion des fenêtres :
   - Division verticale pour l'édition parallèle de code et documentation
   - Division horizontale pour comparer différentes parties de fichiers
   - Fenêtres multiples pour consulter des documents de référence

## Configuration

Helix peut être configuré via :
- `~/.config/helix/config.toml` - paramètres généraux
- `~/.config/helix/languages.toml` - paramètres spécifiques aux langages

Pour les options de configuration détaillées, consultez la documentation officielle.

## Résumé

Helix est un éditeur de texte puissant et moderne qui :
- Utilise l'édition modale pour l'efficacité
- Fournit une gestion riche des commandes et fonctions
- Supporte les curseurs et sélections multiples
- Permet une gestion flexible des fenêtres
- Est configurable et extensible

Pour une utilisation efficace :
1. Apprendre les commandes de base de mouvement et d'édition
2. Maîtriser progressivement les fonctionnalités avancées
3. Développer une configuration adaptée à vos flux de travail
4. Pratiquer régulièrement l'utilisation des nouvelles commandes
