# AGENTS.md

## Architecture

Site 100 % statique — pas de framework, pas de bundler. Netlify sert directement les fichiers HTML/CSS.

## Fichiers clés

| Fichier | Rôle |
|---|---|
| `index.html` | Page unique avec navigation, hero, services, galerie, avis, contact |
| `style.css` | Styles globaux (variables CSS `--bleu` et `--or`) |
| `merci.html` | Page de confirmation Netlify Forms (action du formulaire) |

## Formulaire de contact

Le formulaire utilise **Netlify Forms** (`data-netlify="true"`, `method="POST"`). Il redirige vers `/merci.html` après soumission. La détection se fait au moment du build par le bot Netlify qui analyse le HTML statique — aucune configuration supplémentaire n'est nécessaire.

## Conventions

- Pas de JavaScript côté client
- Variables CSS dans `:root` pour les couleurs de marque
- Classes `.container`, `.grid`, `.card`, `.alt` pour la mise en page
- Responsive via `grid-template-columns: repeat(auto-fit, minmax(...))`
