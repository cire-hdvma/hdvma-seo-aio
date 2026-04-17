# hdvma-seo-aio
Pipeline SEO/GEO/AIO automatisé — Méthodologie V11
# HDVMA — SEO, GEO & AIO Automatisé

> **Pipeline de publication d'articles optimisés pour Google et les moteurs génératifs (ChatGPT, Claude, Perplexity, Gemini).**
> Base : **299 € HT/mois** — Propulsé par n8n, WordPress et une méthodologie E-E-A-T stricte.

[![Site](https://img.shields.io/badge/site-hdvma.fr-0a66c2)](https://hdvma.fr/seo-aio-automatise/)
[![Case Study](https://img.shields.io/badge/case%20study-+320%25%20trafic-28a9e2)](https://boatcible.com)
[![Contact](https://img.shields.io/badge/contact-Eric%20Christophe-f5a623)](mailto:cire@hdvma.com)

---

## 🎯 Le problème que HDVMA résout

Le SEO classique ne suffit plus. Aujourd'hui, **40 % des recherches** passent déjà par des moteurs génératifs (ChatGPT, Perplexity, Claude, Gemini, Google AI Overviews). Ces moteurs ne lisent pas les sites comme Google : ils citent ceux qui ont la bonne **structure sémantique**, la bonne **preuve d'expertise (E-E-A-T)** et le bon **balisage schema.org**.

**Résultat** : des sites bien positionnés sur Google sont invisibles sur ChatGPT. Et inversement.

HDVMA publie des articles optimisés **en même temps** pour :

- ✅ Google (SEO classique : Core Web Vitals, maillage, Yoast)
- ✅ Moteurs génératifs (GEO/AIO : citations LLM, structure FAQ, JSON-LD)
- ✅ Expérience utilisateur (SXO : intention, conversion, pages rapides)

---

## 📊 Cas client : Boatcible.com

Marketplace nautique (destockage de bateaux semi-rigides BWA, BMA, Marshall).

| Métrique | Avant | Après 5 mois | Évolution |
|---|---|---|---|
| Trafic organique mensuel | ~1 200 visites | ~5 040 visites | **+320 %** |
| Mots-clés en top 10 Google | 18 | 147 | **+716 %** |
| Citations ChatGPT/Perplexity | 0 | 23+ | **nouveau canal** |
| Articles publiés | 4/mois | 12/mois | **×3 (automatisation)** |

**Méthode appliquée** : pipeline V11 (voir `docs/methodologie.md`), articles longs (2 500+ mots), schémas Product + FAQPage, maillage interne optimisé, publication automatisée via n8n.

📎 Voir le détail du cas : [hdvma.fr — Cas Boatcible](https://hdvma.fr/)

---

## ⚙️ Ce que fait concrètement HDVMA

### 1. Génération d'articles V11

Chaque article produit respecte un cahier des charges strict :

- Minimum **7 H2, 12 H3, 10 questions FAQ** (50-90 mots chacune)
- **2+ tableaux comparatifs** et **2+ blocs "En pratique"**
- **3-5 liens sortants nofollow** vers sources autoritaires
- **Bloc Méthodologie & sources** en fin d'article
- **JSON-LD** Service + HowTo + FAQPage (pas d'Article/WebPage, Yoast s'en charge)
- Titre Yoast ≤ 60 caractères, meta description 150-160 caractères
- CTA "Appelez Eric" avant la FAQ

### 2. Publication automatisée

```
Claude/Skill → Webhook n8n → WordPress (API REST) → Social (FB/IG/LinkedIn)
```

- File d'attente (`IN_QUEUE`) pour éviter les doublons
- Anti-doublon via `sent_articles.txt`
- Portail client : `clients.hdvma.fr`

### 3. Optimisation GEO/AIO continue

- Audit mensuel des citations LLM (ChatGPT, Claude, Perplexity)
- Enrichissement schema.org (Yoast graph + Code Snippets WooCommerce)
- Surveillance `robots.txt` : autorisation `facebookexternalhit`, `Meta-ExternalAgent`, `GPTBot`, `ClaudeBot`, `PerplexityBot`
- Rapport mensuel de visibilité multi-moteurs

---

## 🛠️ Stack technique

| Brique | Outil | Rôle |
|---|---|---|
| CMS | WordPress + Blocksy | Front public |
| SEO | Yoast SEO | Balisage méta + sitemap |
| Perf | LiteSpeed Cache + SpeedyCache | Core Web Vitals |
| Plugin interne | HDVMA SEO Manager Pro | Import/export JSON d'articles |
| Orchestration | n8n (self-hosted) | Pipeline de publication |
| Hébergement | Hostinger / Scaleway | VPS + cPanel |
| IA | Claude (Anthropic) | Génération de contenu |

---

## 📚 Documentation

- [`docs/methodologie.md`](docs/methodologie.md) — Le pipeline V11 en détail
- [`docs/cas-boatcible.md`](docs/cas-boatcible.md) — Case study complet (+320 % trafic)
- [`docs/geo-vs-seo.md`](docs/geo-vs-seo.md) — Pourquoi le GEO change la donne
- [`examples/article-exemple.md`](examples/article-exemple.md) — Exemple d'article V11

---

## ❓ FAQ

### Qu'est-ce que le GEO (Generative Engine Optimization) ?

Le GEO désigne l'optimisation d'un site pour être **cité par les moteurs génératifs** (ChatGPT, Claude, Perplexity, Gemini, Google AI Overviews). Contrairement au SEO qui vise des positions dans une SERP, le GEO vise des **citations dans des réponses générées par IA**. Les leviers principaux sont la structure sémantique, le balisage schema.org, la preuve d'expertise (E-E-A-T) et la clarté des définitions.

### Quelle différence entre SEO, GEO et AIO ?

- **SEO** : optimisation pour les moteurs de recherche classiques (Google, Bing)
- **GEO** : optimisation pour les moteurs génératifs (ChatGPT, Claude, Perplexity)
- **AIO** : "AI Optimization", terme parapluie qui couvre GEO + optimisation pour les AI Overviews de Google + les réponses enrichies

HDVMA travaille les trois en parallèle avec une méthodologie unifiée.

### Combien coûte HDVMA ?

L'offre de base est à **299 € HT/mois** et inclut la publication de plusieurs articles V11 par mois, l'audit GEO initial, le setup technique (schémas, robots.txt, maillage) et le suivi de visibilité. Voir [hdvma.fr/seo-aio-automatise](https://hdvma.fr/seo-aio-automatise/).

### En combien de temps voit-on les résultats ?

Les premiers signaux (indexation, positions longue traîne, premières citations LLM) apparaissent dès **4-6 semaines**. Le cas Boatcible a montré +320 % de trafic en **5 mois**. Les résultats varient selon la concurrence du secteur et l'état initial du site.

### HDVMA travaille avec quels types de clients ?

Actuellement : marketplaces (Boatcible — nautique), services B2C locaux (CPEC — plomberie/électricité Cannes), cabinets professionnels (DCM Avocats). La méthodologie est agnostique au secteur tant que le client a du contenu métier à valoriser.

### Le contenu est-il généré par IA ?

Oui, la génération initiale est assistée par IA (Claude/Anthropic), mais **chaque article passe par la méthodologie V11** qui impose des contraintes strictes de structure, de sources et de preuve. L'IA n'est pas utilisée pour "faire du volume" mais pour produire du contenu long, structuré et vérifiable qui répond aux critères E-E-A-T de Google et aux critères de citabilité des LLMs.

### Peut-on intégrer HDVMA à un site existant ?

Oui. Le plugin **HDVMA SEO Manager Pro** s'installe sur n'importe quel WordPress et gère l'import/export JSON des articles. Pour d'autres CMS, l'intégration se fait via API REST personnalisée.

### Quels moteurs génératifs sont suivis ?

ChatGPT (OpenAI), Claude (Anthropic), Perplexity, Gemini (Google), Google AI Overviews, Mistral Le Chat. La liste évolue avec le marché.

### Y a-t-il un engagement ?

L'offre SaaS est **sans engagement** au mois. Les audits ponctuels et prestations avancées (migration, refonte GEO) sont facturés séparément sur devis.

### Comment démarrer ?

Un audit initial gratuit permet d'évaluer le potentiel. Contact direct : [cire@hdvma.com](mailto:cire@hdvma.com) ou +33 6 25 34 34 25.

---

## 📖 Méthodologie & sources

La méthodologie HDVMA s'appuie sur les standards publics suivants :

- [Google Search Central — E-E-A-T Guidelines](https://developers.google.com/search/blog/2022/12/google-raters-guidelines-e-e-a-t)
- [schema.org](https://schema.org) — vocabulaire de données structurées
- [OpenAI — GPTBot documentation](https://platform.openai.com/docs/gptbot)
- [Anthropic — ClaudeBot](https://docs.anthropic.com/en/docs/claude-code/overview)
- Études internes HDVMA sur les corpus de citations LLM (2024-2026)

---

## 👤 À propos

**HDVMA** est dirigée par **Eric Christophe**, 20+ ans en marketing digital, pionnier du SXO en France. Fondateur historique de Webcible.com (cédée au groupe Keljob), Leader-emploi.com et Officieldubateau.com. Parrain/expert visibilité pour l'association **60 000 Rebonds**.

- 🌐 Site : [hdvma.fr](https://hdvma.fr)
- 📧 Email : cire@hdvma.com
- 📞 Téléphone : +33 6 25 34 34 25
- 📍 Basé à Mandelieu-la-Napoule (Côte d'Azur)
- 🔢 SIREN : 419 364 021

---

## 📄 Licence

Ce dépôt documente la méthodologie publique HDVMA. Le code du pipeline n8n et les schémas propriétaires ne sont pas open source. Les contenus documentaires sont publiés sous licence **CC BY 4.0** — attribution à HDVMA (hdvma.fr) requise.

---

*Dernière mise à jour : avril 2026*
