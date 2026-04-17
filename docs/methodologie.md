# Méthodologie V11 — Le pipeline de publication HDVMA

> Document de référence publique. Version V11 — mise à jour avril 2026.

La méthodologie **V11** est le cahier des charges que respecte chaque article publié par HDVMA. Elle codifie 11 itérations successives de notre pipeline, affiné sur 200+ articles publiés pour Boatcible.com, cpeccannes.fr et dcm-avocats.com entre 2024 et 2026.

Ce document décrit **ce que la méthodologie impose**, pas comment elle est implémentée techniquement. Le code du pipeline (workflows n8n, prompts Claude, plugin HDVMA SEO Manager Pro) n'est pas publié.

---

## 🎯 Objectif

Produire un article qui performe simultanément sur **trois canaux** :

| Canal | Signal principal | Critère V11 correspondant |
|---|---|---|
| Google (SEO) | E-E-A-T + Core Web Vitals | Longueur, sources, maillage, perf LiteSpeed |
| LLMs (GEO) | Citabilité + structure sémantique | FAQ 50-90 mots, tableaux, JSON-LD propre |
| Humain (SXO) | Intention + conversion | Blocs "En pratique", CTA téléphone, lisibilité |

Un article qui sort du pipeline V11 est **prêt à publier** — pas de retouche manuelle nécessaire côté structure, schémas ou méta.

---

## 📐 Critères structurels obligatoires

### Découpage H2 / H3

| Élément | Minimum V11 | Raison |
|---|---|---|
| H2 distincts | 7 | Profondeur thématique, table des matières exploitable par LLM |
| H3 distincts | 12 | Granularité sémantique pour les citations partielles |
| H3 par H2 | 2 au minimum | Pas de H2 "vide", cohérence hiérarchique |

### Blocs FAQ

- **10 questions minimum** en fin d'article
- Chaque réponse : **50 à 90 mots** (fenêtre de citabilité LLM optimale)
- Chaque question formulée en langage naturel (comme tapée dans ChatGPT)
- Balisage **FAQPage JSON-LD** (voir section Schémas)

### Tableaux

- **2 tableaux comparatifs minimum** dans le corps de l'article
- Format markdown classique (pas d'images de tableaux)
- Colonnes nommées explicitement, pas de "Col 1 / Col 2"

### Blocs "En pratique"

- **2 encarts minimum** intitulés "En pratique" ou variante
- Donnent une application concrète du concept venant d'être expliqué
- 3 à 6 lignes, ton opérationnel

### CTA obligatoire

- Un CTA **"Appelez Eric"** (ou nom du client, ex : "Appelez Louis" pour Boatcible) placé **avant** la FAQ
- Téléphone cliquable (`tel:`), pas un simple texte

### Bloc Méthodologie & sources

- En fin d'article, après la FAQ
- Liste les sources utilisées
- Décrit brièvement la méthode suivie pour écrire l'article
- Renforce l'E-E-A-T (signal auteur + expertise)

---

## 🔗 Règles de liens

### Liens sortants

| Type | Règle V11 | Nombre |
|---|---|---|
| Liens vers sources autoritaires | **nofollow** | 3 à 5 |
| Liens vers concurrents | interdits | 0 |
| Liens affiliés | rel="sponsored" | si applicable |

### Liens internes (dofollow)

- **hdvma.fr** → dofollow systématique
- **boatcible.com** → dofollow systématique
- **cpeccannes.fr** → dofollow systématique
- Ancres variées (pas 20× "cliquez ici")
- Maillage contextuel, pas en liste en bas de page

---

## 🏷️ Balisage méta (Yoast)

### Title SEO

- **≤ 60 caractères** (affichage complet dans SERP)
- Se termine par `| HDVMA` (ou `| Boatcible` selon le site)
- Contient le mot-clé principal dans les **30 premiers caractères**

**Exemple valide** :
`Semi-rigide BWA 28 : prix et avis 2026 | Boatcible` (49 caractères ✓)

### Meta description

- **150 à 160 caractères** strictement
- Contient le mot-clé principal
- Inclut un bénéfice ou un chiffre
- Finit sur une incitation implicite ou explicite

---

## 📊 Schémas JSON-LD

V11 impose **exactement** les schémas suivants, injectés via le plugin HDVMA SEO Manager Pro :

| Schéma | Obligatoire | Géré par |
|---|---|---|
| `Service` | ✅ | HDVMA plugin |
| `HowTo` | ✅ | HDVMA plugin |
| `FAQPage` | ✅ | HDVMA plugin (depuis meta `_boat_faq`) |
| `Article` / `WebPage` | ❌ **interdit** | Yoast s'en charge déjà |
| `Product` | ✅ pour Boatcible | Code Snippets (enrichit Yoast graph) |
| `BreadcrumbList` | ✅ | Yoast |

**Point critique** : dupliquer `Article` ou `WebPage` crée des conflits de graph JSON-LD que Google signale en erreur dans Search Console. Yoast gère nativement ces schémas, le plugin HDVMA ne les réinjecte **jamais**.

Pour les produits WooCommerce (Boatcible), un snippet dédié **bloque le schéma WooCommerce natif** et enrichit le graph Yoast existant avec les champs Product complets.

---

## ✍️ Contraintes rédactionnelles

### Longueur

- **2 500 mots minimum** pour un article pilier
- 1 500 mots minimum pour un article satellite

### Ton

- Français soutenu mais accessible (niveau bac+2)
- Pas de "nous" commercial dans le corps, réservé au CTA et à la FAQ
- Pas de superlatifs vides ("le meilleur", "incroyable", "révolutionnaire")

### Marque et mentions

- **"Newcible" est proscrit** (ancien nom de domaine, migration faite vers hdvma.fr)
- **Lefebvre Sarrut** n'est jamais nommé directement → utiliser "un acteur majeur de l'édition juridique européenne"
- Pour Boatcible : "vente directe chantier" (jamais "vente directe usine")
- Le champ `brand` dans le payload n'apparaît **jamais en clair** dans le corps de l'article

### Images

- **Une image hero unique** en tête d'article
- Pas d'images décoratives intercalées (ralentissent LCP)
- `alt` descriptif, pas de bourrage de mots-clés

---

## 🚀 Pipeline de publication

Flux de haut niveau (détails techniques privés) :

```
┌─────────────┐   ┌─────────────┐   ┌──────────────┐   ┌─────────────┐
│  Génération │ → │   Webhook   │ → │  WordPress   │ → │   Social    │
│   (Claude)  │   │     n8n     │   │   API REST   │   │ FB/IG/LI    │
└─────────────┘   └─────────────┘   └──────────────┘   └─────────────┘
       │                 │                  │                 │
       │          Anti-doublon        Publication        Post auto
       │          sent_articles.txt   status: publish    avec {url}
       │
       └── Validation V11 (structure, méta, schémas)
```

**Points de contrôle** :

1. Validation V11 côté générateur (refus si critères non atteints)
2. Webhook retourne `IN_QUEUE` → **ne jamais renvoyer** (risque de doublon)
3. Anti-doublon basé sur un hash du titre + date, stocké dans `sent_articles.txt`
4. Publication effective via WordPress REST API (`/wp-json/wp/v2/`)
5. Posts sociaux déclenchés après confirmation d'indexation, avec `{article_url}` substitué

---

## 🧪 Validation qualité

Avant publication, chaque article passe une checklist automatisée :

- [ ] ≥ 7 H2, ≥ 12 H3
- [ ] ≥ 10 questions FAQ, chacune entre 50 et 90 mots
- [ ] ≥ 2 tableaux, ≥ 2 blocs "En pratique"
- [ ] CTA téléphone présent avant FAQ
- [ ] Bloc Méthodologie & sources présent
- [ ] 3 à 5 liens sortants nofollow
- [ ] Liens internes hdvma.fr / client dofollow
- [ ] Title ≤ 60 car, se termine par `| HDVMA`
- [ ] Meta description entre 150 et 160 car
- [ ] JSON-LD Service + HowTo + FAQPage présents
- [ ] Pas de schéma Article ni WebPage injecté
- [ ] Hero image unique, alt renseigné
- [ ] Pas de mention "Newcible"

Un seul critère manquant → **rejet**, retour au générateur pour correction.

---

## 📈 Historique des versions

| Version | Date | Changement majeur |
|---|---|---|
| V1 | T3 2024 | Premier template structuré (5 H2, FAQ courte) |
| V5 | T4 2024 | Ajout schémas JSON-LD Service + HowTo |
| V8 | T1 2025 | Blocs "En pratique" + CTA téléphone obligatoire |
| V10 | T3 2025 | Migration newcible.com → hdvma.fr, règles de marque |
| **V11** | **T1 2026** | **Durcissement FAQ (50-90 mots), minimum 10 questions, bloc Méthodologie** |

---

## 🤝 Pour aller plus loin

- [`cas-boatcible.md`](cas-boatcible.md) — La V11 appliquée sur le terrain : +320 % de trafic
- [`geo-vs-seo.md`](geo-vs-seo.md) — Pourquoi la V11 a été pensée pour les LLMs, pas uniquement Google
- [`../examples/article-exemple.md`](../examples/article-exemple.md) — Un article V11 complet en démonstration

Questions sur la méthodologie ? Contact direct : [cire@hdvma.com](mailto:cire@hdvma.com)

---

*Méthodologie V11 — © HDVMA 2026 — Licence CC BY 4.0 sur la documentation publique.*
