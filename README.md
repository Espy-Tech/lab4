# Exercice 4 — Mise en page responsive avec Bootstrap

## Objectif

Reprendre la page de l’exercice 3 et la mettre en page à l’aide d’un framework CSS. Cette page utilise **Bootstrap 5.3.3** pour organiser son contenu en grille, adapter son affichage aux différentes tailles d’écran et gérer les espacements.

La page est réalisée en HTML et CSS, sans React ni étape de compilation.

## Ouvrir la page

Ouvrir `index.html` dans un navigateur. Bootstrap et la police de caractères sont chargés depuis des CDN : une connexion Internet est donc nécessaire pour afficher tous les styles.

## Organisation des fichiers

- `index.html` contient le contenu, les sections, les classes Bootstrap et la structure responsive.
- `style.css` contient les couleurs et les personnalisations propres à cette page.
- `image.png` est le logo affiché dans l’en-tête.
- `image.jpg` est l’image cliquable de la section des liens.

## Organisation de la page

La page est constituée de trois sections principales :

1. **Liste de liens** (`#links`) : différents types de liens et une image cliquable.
2. **Tableau** (`#tableau`) : notes et résultats, dans un conteneur qui permet le défilement horizontal sur les petits écrans.
3. **Formulaire** (`#formulaire`) : champs d’identité et de contact, date, choix du sexe, langage de programmation, biographie et case d’acceptation.

L’en-tête contient le logo et le titre. La navigation permet d’accéder directement aux trois sections. Le pied de page ferme la page.

## Comprendre la grille Bootstrap

La grille Bootstrap s’appuie principalement sur `container`, `row` et `col-*` :

```html
<main class="container">
    <div class="row g-3 g-lg-4">
        <section class="col-12 col-lg-6">...</section>
        <section class="col-12 col-lg-6">...</section>
    </div>
</main>
```

- `container` centre le contenu et limite sa largeur.
- `row` crée une rangée de colonnes.
- `col-12` fait occuper toute la largeur à la section.
- `col-lg-6` fait occuper la moitié de la rangée à partir du breakpoint `lg`.
- `g-3` et `g-lg-4` règlent l’espace entre les colonnes et les rangées.

Les deux premières sections sont donc empilées sur téléphone, puis affichées côte à côte sur grand écran. La section du formulaire utilise `col-12` et occupe une rangée complète.

## Principe Mobile First

Mobile First signifie que l’on commence par définir une mise en page adaptée aux petits écrans, puis que l’on ajoute des adaptations pour les écrans plus larges.

Dans Bootstrap, une classe sans breakpoint s’applique dès la plus petite taille. Une classe préfixée par un breakpoint s’applique à partir de celui-ci. Par exemple :

- `col-12` : largeur complète dès le mobile ;
- `col-lg-6` : demi-largeur à partir du breakpoint `lg` ;
- `col-12 col-md-6` : largeur complète sur mobile, demi-largeur à partir de `md`.

Le formulaire suit cette logique : ses champs sont empilés sur mobile et plusieurs champs passent côte à côte à partir de `md`.

## Espacements et composants Bootstrap

Les marges et les espacements intérieurs sont gérés avec les classes Bootstrap plutôt qu’avec des règles CSS personnalisées :

- `py-3` ajoute un espacement vertical ;
- `p-3` ajoute un espacement intérieur sur tous les côtés ;
- `mb-3` ajoute une marge sous un élément ;
- `g-3` règle l’écart d’une grille ;
- `py-md-4` augmente l’espacement vertical à partir de `md`.

La page utilise également quelques composants Bootstrap :

- `card`, `card-body` et `shadow-sm` pour présenter chaque section ;
- `table`, `table-striped` et `table-hover` pour le tableau ;
- `form-control`, `form-check` et `form-label` pour le formulaire ;
- `btn btn-primary` pour le bouton d’envoi ;
- `d-flex`, `gap-2` et `text-center` pour l’alignement et la présentation.

`style.css` complète Bootstrap avec les couleurs, les bordures et les détails visuels spécifiques à la page.
