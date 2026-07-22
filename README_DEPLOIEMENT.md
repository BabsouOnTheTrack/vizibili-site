# SITE STATIQUE VIZIBILI.FR — GUIDE DE DÉPLOIEMENT

**Version :** 1.0 · 22/07/2026 · Produit par SOP_SITE_VITRINE_LOCAL, Phase B, étape 4
**Référence visuelle :** maquette v2 (fait foi pour le rendu)

## Contenu du dossier

```
site/
├── index.html                    Accueil
├── offre/index.html              Offre
├── cas-clients/index.html        Preuve (4 cas clients)
├── contact/index.html            Contact
├── mentions-legales/index.html   Mentions légales (À COMPLÉTER avant mise en ligne)
├── sitemap.xml                   Plan du site (à soumettre en Search Console, Phase C)
├── robots.txt
├── assets/
│   ├── styles.css                Feuille de style unique
│   ├── logo-vizibili.png         Logo optimisé (17 Ko)
│   ├── favicon.png
│   └── apple-touch-icon.png
└── fonts/                        VIDE : voir étape 2 ci-dessous
```

## Étape 1 — Choisir l'hébergement

Tout hébergement statique convient. Deux familles :

- **Hébergeur mutualisé français** (o2switch, Infomaniak...) : dépôt des fichiers par FTP dans le dossier web. Simple, souverain, adapté si une messagerie doit cohabiter.
- **Plateforme statique** (Cloudflare Pages, Netlify) : gratuit, HTTPS automatique, très performant. Nécessitera de bien gérer les DNS à la bascule (voir avertissement).

**Avertissement DNS (leçon gravée, SOP étape 8) : quelle que soit l'option, la bascule DNS finale devra impérativement préserver les enregistrements MX de la messagerie professionnelle.** Ne jamais faire pointer le domaine entier vers une plateforme sans reporter les MX existants.

## Étape 2 — Polices locales : RÉSOLU (22/07/2026)

Les 4 fichiers woff2 (Archivo 700/800, Inter 400/600, jeu latin) sont **inclus dans `/fonts/`** — signature binaire vérifiée, ~77 Ko au total. Les deux polices critiques (archivo-800, inter-400) sont préchargées dans le `<head>` de chaque page. Rien à faire.

## Étape 3 — Compléter les mentions légales

`mentions-legales/index.html` contient des champs [À COMPLÉTER] : dénomination, SIREN, adresse, directeur de publication, hébergeur retenu. **Obligation légale — bloquant pour la mise en ligne publique**, pas pour la préproduction.

## Étape 4 — Mettre en préproduction

Déployer sur une URL de test (sous-domaine de test, URL Cloudflare/Netlify temporaire...). **Ne pas toucher au DNS de vizibili.fr à ce stade** — le site Shopify actuel reste en ligne jusqu'à la bascule (Phase C).

## Étape 5 — Demander la recette

Transmettre l'URL de préproduction pour la recette qualité (étape 5 de la SOP) : elle sera jugée **uniquement sur PageSpeed Insights** (jamais le Lighthouse local), plus une vérification de conformité au registre éditorial et à la maquette.

## Rappels de périmètre

- Aucun script tiers, aucun cookie : ne pas ajouter d'analytics sans décision consignée.
- Le lien Calendly est en lien direct (pas de widget embarqué) : c'est voulu, pour la performance.
- Les textes sont conformes au registre validé (voix « je », vouvoiement, sans tiret cadratin) : toute retouche de texte doit repasser par le registre.
