# 🎂 Joyeux Anniversaire Julie Raïssa

Site d'anniversaire animé, réalisé par **Benoit** pour sa grande sœur Julie Raïssa (11 octobre 2026).

## Aperçu

- **Enveloppe surprise** : un sceau « JR » à ouvrir, qui lance la musique et une pluie de confettis
- **Titre animé** : « Joyeux Anniversaire » révélé lettre par lettre, prénom en or brillant
- **Bougies à souffler** : on touche chaque flamme (fumée, puis feu d'artifice)
- **Galerie** de 8 photos avec apparition au défilement, effet 3D au survol et visionneuse plein écran (balayage sur mobile)
- **Lettre** à la grande sœur, révélée ligne par ligne
- **Film d'anniversaire** (vidéo de 48 s)
- **Finale** avec feu d'artifice à la demande et bouton « Copier le lien »
- Poussière d'or animée en fond, musique avec bouton marche/arrêt

## Technologies

- HTML, CSS et JavaScript natifs, sans framework ni build
- Canvas 2D pour les particules, les feux d'artifice et les confettis
- Polices Google Fonts : Great Vibes, Cormorant Garamond, Montserrat
- Responsive (mobile d'abord) et compatible `prefers-reduced-motion`

## Structure

```
julie-raissa/
├── index.html        # page complète (HTML + CSS + JS)
├── vercel.json       # cache des images et vidéos
├── img/
│   ├── p1.webp … p8.webp   # photos de la galerie
│   ├── poster.jpg          # affiche de la vidéo
│   └── og.jpg              # aperçu du lien (WhatsApp, Facebook…)
└── media/
    ├── film.mp4            # film d'anniversaire
    └── musique.mp3         # musique de fond
```

## Lancer en local

```bash
cd julie-raissa
npx serve .
```

Ouvre ensuite http://localhost:3000.

> Évite d'ouvrir `index.html` en double-cliquant dessus : la vidéo et la musique se chargent mieux avec un serveur local.

## Déployer sur Vercel

```bash
cd julie-raissa
npx vercel --prod
```

Ou passe par GitHub : pousse le dossier, puis importe le dépôt sur vercel.com (Framework : **Other**, sans commande de build).

### Après le déploiement : aperçu WhatsApp

WhatsApp exige l'adresse complète de l'image d'aperçu. Dans `index.html`, remplace :

```html
<meta property="og:image" content="/img/og.jpg" />
```

par :

```html
<meta property="og:image" content="https://TON-LIEN.vercel.app/img/og.jpg" />
```

Puis redéploie avec `npx vercel --prod`.

## Personnaliser

| Élément | Où le modifier dans `index.html` |
|---|---|
| Photos et légendes | tableau `PHOTOS` dans le `<script>` |
| Mots du ruban défilant | tableau `WORDS` |
| Texte de la lettre | section `id="lettre"` |
| Vœux après les bougies | tableau `WISHES` |
| Couleurs et polices | variables CSS dans `:root` |
| Musique | remplacer `media/musique.mp3` (même nom) |

---

Conçu et développé avec ❤️ par **Benoit**
