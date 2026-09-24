# parapheur-schema-builder

Application web permettant de construire et de générer automatiquement des documents décrivant des circuits de parapheur.

L'outil transforme une description textuelle et structurée d'une arborescence en un document comprenant notamment un **référentiel**, un **schéma graphique du circuit** et une **mise en page finale au format PDF**.

## Présentation

`parapheur-schema-builder` a été développé afin de simplifier la création de documents représentant les circuits de parapheur.

La structure du circuit est saisie sous forme de texte. **L'indentation définit la hiérarchie et les différents embranchements de l'arborescence.**

À partir de cette structure, l'application permet progressivement de :

- construire l'arborescence du circuit ;
- identifier les circuits et les bureaux utilisés ;
- renseigner leur libellé ou sous-type ;
- générer le schéma graphique correspondant ;
- prévisualiser le tableau récapitulatif ;
- générer le document final.

> **L'outil n'utilise pas d'intelligence artificielle.** La structure du circuit est déterminée à partir des données saisies et de leur indentation.

## Contexte

La création de ces documents était auparavant réalisée manuellement, à l'aide de différents outils bureautiques ou graphiques tels que Microsoft Word ou GIMP.

Cette méthode pouvait devenir chronophage lorsque plusieurs dizaines de documents devaient être produits, notamment pour des ajustements de mise en page ou de présentation : centrage, alignement, espacement, positionnement des éléments, etc.

L'objectif de `parapheur-schema-builder` est d'automatiser cette production à partir d'une description structurée du circuit.

## Fonctionnement

### 1. Saisie de l'arborescence

L'arborescence est saisie sous forme de texte.

Chaque niveau d'indentation représente un niveau hiérarchique dans le circuit.

Par exemple :

```text
BUR0153
	CIR0230
		BUR0158
			BUR0156
	CIR0229
		BUR0158
```

Cette structure peut être représentée de manière simplifiée ainsi :

```text
BUR0153
├── CIR0230
│   └── BUR0158
│       └── BUR0156
└── CIR0229
    └── BUR0158
```

L'indentation permet notamment de représenter les embranchements d'un circuit.

### 2. Construction du référentiel

À partir de l'arborescence saisie, l'application identifie les différents éléments utilisés dans le circuit.

Le référentiel permet ensuite de renseigner les informations associées à ces éléments, notamment :

- les **circuits** et leur sous-type ;
- les **bureaux** et leur intitulé.

Par exemple :

| Élément | Libellé |
| --- | --- |
| `CIR0230` | Circuit de signature n°0230 |
| `CIR0229` | Circuit de signature n°0229 |
| `BUR0153` | Bureau du secrétariat général |
| `BUR0158` | Bureau des RHs |
| `BUR0156` | Bureau de la présidence |

Le référentiel est ensuite intégré au document final.

### 3. Génération du schéma

L'application génère une représentation graphique de l'arborescence.

Le schéma permet de visualiser :

- les différents bureaux ;
- les circuits ;
- les embranchements ;
- l'enchaînement des étapes ;
- les points de sortie du circuit.

Une représentation intermédiaire sous forme de **code Mermaid** peut également être consultée et copiée.

### 4. Prévisualisation du tableau

Une prévisualisation du tableau récapitulatif permet de vérifier le rendu du référentiel avant la génération du document final.

### 5. Génération du document final

Une fois les différentes informations renseignées et vérifiées, l'application génère le document complet.

Le document final regroupe notamment :

- le titre du document ;
- le référentiel ;
- le schéma graphique du circuit.

## Fonctionnalités

- Saisie d'une arborescence sous forme de texte indenté
- Gestion des niveaux hiérarchiques et des embranchements
- Construction d'un référentiel
- Renseignement des libellés et sous-types
- Génération automatique du schéma
- Génération du code Mermaid
- Copie du code Mermaid
- Prévisualisation du schéma
- Prévisualisation du tableau
- Export du schéma au format SVG
- Génération du document final au format PDF

## Exemple

### Entrée

```text
BUR0153
	CIR0230
		BUR0158
			BUR0156
	CIR0229
		BUR0158
```

### Référentiel

```text
Circuits
- CIR0230 : Circuit de signature n°0230
- CIR0229 : Circuit de signature n°0229

Bureaux
- BUR0153 : Bureau du secrétariat général
- BUR0158 : Bureau des RHs
- BUR0156 : Bureau de la présidence
```

### Structure obtenue

```text
BUR0153
├── CIR0230
│   └── BUR0158
│       └── BUR0156
└── CIR0229
    └── BUR0158
```

L'application génère ensuite le schéma graphique et le document final à partir de ces informations.

## Utilisation

L'application s'utilise depuis une interface web.
Il suffit d'ouvrir le fichier .html dans un navigateur.

Le processus général est le suivant :

1. **Saisir l'arborescence** du circuit.
2. **Générer le schéma** afin d'analyser la structure fournie.
3. **Renseigner le référentiel** en complétant les libellés des circuits et des bureaux.
4. **Générer le tableau final** et vérifier son rendu.
5. **Renseigner le titre** du document.
6. **Générer le document complet**.

## Technologie

- [JavaScript](https://developer.mozilla.org/fr/docs/Web/JavaScript)
- [Mermaid](https://mermaid.js.org/)
- HTML / CSS
- Génération de documents PDF

> N'utilise pas d'intelligence artificielle.

## Contexte du dépôt

Ce dépôt contient le code source d'un outil développé en interne pour les besoins de la **collectivité territoriale de l'Orne**.

Les sources sont partagées dans une démarche de mutualisation et de partage des développements réalisés en interne.

Ce dépôt peut notamment permettre :

- de consulter le fonctionnement de l'outil ;
- de comprendre les choix réalisés lors de son développement ;
- de réutiliser certains éléments du code ;
- de s'inspirer de la solution pour d'autres besoins.

## Maintenance et support

Ce projet est un développement interne et est partagé **sans engagement de maintenance, de support ou de mise à jour**.

La mise à disposition du code source ne constitue pas un engagement de compatibilité avec les futures versions des navigateurs, dépendances, bibliothèques ou environnements d'exécution.

Les éventuelles évolutions du projet dépendent des besoins internes de la collectivité et des ressources disponibles.

## Licence

Ce projet est distribué sous licence **GNU General Public License v3.0 (GPL-3.0)**.

Voir le fichier [`LICENSE`](LICENSE) pour consulter le texte complet de la licence.

## Auteur

Ce projet a été développé en interne par **Vincent Bourgmayer** pour les besoins de la **collectivité territoriale de l'Orne**.

- Profil GitHub : [@vince-bourgmayer](https://github.com/vince-bourgmayer)


