# Cas Boatcible — +320 % de trafic organique en 5 mois

> Case study public. Période analysée : juillet 2025 – décembre 2025.
> Secteur : marketplace nautique (destockage de bateaux semi-rigides).

**Boatcible.com** est la plateforme e-commerce d'Eric Christophe, spécialisée dans la vente directe chantier de semi-rigides (BWA, BMA, Marshall) auprès de chantiers italiens. C'est aussi le **laboratoire SEO/GEO de HDVMA** : chaque itération de la méthodologie V11 y est testée avant d'être déployée chez les clients.

Ce document documente les résultats obtenus entre juillet et décembre 2025 après application complète du pipeline V11.

---

## 📊 Résultats mesurés

| Métrique | Juillet 2025 (baseline) | Décembre 2025 | Évolution |
|---|---|---|---|
| Trafic organique mensuel | 1 200 visites | 5 040 visites | **+320 %** |
| Impressions Google (GSC) | 48 000 / mois | 287 000 / mois | **+498 %** |
| Mots-clés en top 10 | 18 | 147 | **+716 %** |
| Mots-clés en top 3 | 4 | 32 | **+700 %** |
| Pages indexées | 87 | 214 | **+146 %** |
| Articles publiés | 4/mois | 12/mois | **×3** |
| Citations ChatGPT (audit manuel) | 0 | 23+ | **nouveau canal** |
| Citations Perplexity (audit manuel) | 0 | 15+ | **nouveau canal** |
| Taux de conversion (demande de devis) | 0,8 % | 2,1 % | **+163 %** |

**Outils de mesure** : Google Search Console, Google Analytics 4, Ahrefs, audit manuel mensuel sur ChatGPT et Perplexity (panel de 50 requêtes types du secteur).

---

## 🎯 Contexte de départ

### Situation initiale (juin 2025)

Boatcible.com existait depuis 2024 mais stagnait :

- Site WordPress + WooCommerce sous-exploité
- Articles de blog courts (500-800 mots), publiés de façon irrégulière
- Pas de balisage schema.org au-delà du natif WooCommerce
- Aucun suivi des citations LLM
- Concurrence directe : brokers nautiques établis (iNautia, Boat24, Band of Boats)

### Diagnostic initial

Un audit complet a révélé **7 problèmes majeurs** :

1. **Contenu trop court** pour les requêtes informationnelles longue traîne
2. **Absence de FAQ structurée** sur les fiches produit et articles
3. **Schémas Product** dupliqués (WooCommerce natif + Yoast en conflit)
4. **Robots.txt** bloquant `GPTBot` et `ClaudeBot` par défaut
5. **Maillage interne anarchique**, aucune stratégie de cocon sémantique
6. **Core Web Vitals** en rouge sur mobile (LCP > 4s)
7. **Aucune autorité topique** sur les requêtes "semi-rigide [marque]"

---

## 🛠️ La méthode V11 appliquée — étape par étape

### Étape 1 — Nettoyage technique (semaines 1-2)

**Perf & infrastructure** :

- Migration vers hébergement Hostinger optimisé
- Installation LiteSpeed Cache + SpeedyCache
- Optimisation images (WebP, lazy loading, dimensions fixes)
- Résultat : LCP 4,2s → 1,8s sur mobile

**Robots.txt** réécrit pour autoriser explicitement :

```
User-agent: GPTBot
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: Meta-ExternalAgent
Allow: /

User-agent: facebookexternalhit
Allow: /
```

**Schémas JSON-LD** :

- Désactivation du schéma WooCommerce natif (via Code Snippets PHP)
- Enrichissement du graph Yoast avec les champs Product complets
- Ajout du meta field `_boat_faq` pour générer automatiquement le FAQPage

### Étape 2 — Stratégie éditoriale (semaine 3)

Cartographie des intentions de recherche en **4 niveaux** :

| Niveau | Type | Exemple | Format V11 |
|---|---|---|---|
| 1 | Transactionnel | "BWA 28 prix" | Fiche produit enrichie |
| 2 | Navigationnel | "Boatcible avis" | Page marque + témoignages |
| 3 | Informationnel | "comment choisir un semi-rigide" | Article V11 pilier |
| 4 | Comparatif | "BWA vs Marshall" | Article V11 comparatif avec tableaux |

**Priorité donnée aux niveaux 3 et 4** : ce sont eux qui génèrent les citations LLM, les articles de niveau 1-2 étant déjà servis par le catalogue produit.

### Étape 3 — Production V11 (mois 2-5)

Passage de 4 à 12 articles par mois grâce au pipeline automatisé :

- Chaque article : 2 500 à 3 500 mots
- Structure V11 stricte (7 H2, 12 H3, 10 FAQ, 2+ tableaux)
- CTA "Appelez Louis" avant la FAQ (numéro dédié Boatcible)
- Hero image unique, pas de surcharge visuelle
- Publication programmée à 9h les mardis et jeudis

**Exemples d'articles publiés** :

- "Semi-rigide BWA 28 GT : avis, prix et alternatives en 2025"
- "Marshall vs BWA : quel semi-rigide choisir pour la côte méditerranéenne ?"
- "Vente directe chantier : comment ça marche et pourquoi c'est moins cher"
- "Semi-rigide 300 CV : les 5 modèles à connaître avant d'acheter"

### Étape 4 — Maillage et cocons (mois 3-4)

Création de **3 cocons sémantiques** :

1. **Cocon marques** : BWA, BMA, Marshall → chaque marque a un article pilier + 4-6 satellites
2. **Cocon usage** : pêche, famille, sport, charter → articles d'intention
3. **Cocon achat** : financement, assurance, vente directe, livraison → articles de conversion

Maillage interne : chaque satellite renvoie vers le pilier avec ancre exacte, le pilier redistribue vers les satellites avec ancres variées.

### Étape 5 — Suivi et itération (en continu)

**Audit mensuel** des citations LLM :

- Panel de 50 requêtes types saisies manuellement dans ChatGPT, Claude, Perplexity
- Relevé des citations (mention explicite + lien cliquable)
- Ajustement des articles sous-citables : reformulation des définitions, enrichissement FAQ

**Audit mensuel** Google :

- Évolution des positions via Search Console
- Identification des pages à potentiel (impressions élevées, CTR bas → optimisation title/meta)
- Mise à jour des articles pilier tous les 3 mois (fraîcheur + nouvelles questions FAQ)

---

## 📈 Courbe de croissance

```
Trafic organique mensuel (visites)

5000 ┤                                          ╭──●  5 040
4500 ┤                                      ╭───╯
4000 ┤                                  ╭───╯
3500 ┤                              ╭───╯
3000 ┤                          ╭───╯
2500 ┤                      ╭───╯
2000 ┤                  ╭───╯
1500 ┤              ╭───╯
1000 ┤ ●──────●────╯  1 200
 500 ┤
   0 ┼─────┬─────┬─────┬─────┬─────┬─────┬
      Jul   Aug   Sep   Oct   Nov   Dec
```

**Phases observées** :

- **Mois 1-2** : phase technique, effets non visibles sur le trafic (LCP + robots.txt + schémas)
- **Mois 2-3** : premières remontées longue traîne, gain modéré (+40 %)
- **Mois 3-4** : accélération avec les premiers cocons sémantiques matures (+120 %)
- **Mois 4-5** : effet boule de neige — les articles pilier commencent à être cités par les LLMs, ce qui renforce l'autorité Google (+320 % cumulé)

---

## 💡 Les 5 enseignements tirés

### 1. La perf technique est un **prérequis**, pas un levier

Tant que les Core Web Vitals étaient rouges, aucun effort éditorial ne payait. La semaine 1-2 (perf pure) a semblé "improductive" mais sans elle, rien n'aurait démarré.

### 2. Les LLMs et Google se renforcent mutuellement

On s'attendait à ce que le GEO soit un canal **parallèle** au SEO. En réalité, les articles très cités par ChatGPT/Perplexity voient aussi leurs positions Google monter — probablement parce qu'ils cochent les mêmes cases E-E-A-T que Google valorise.

### 3. La FAQ 50-90 mots est la **fenêtre magique**

Les réponses de moins de 40 mots ne sont pas reprises (trop courtes pour faire sens seules). Les réponses de plus de 100 mots sont tronquées ou reformulées. La fenêtre 50-90 est celle où le LLM cite **texto**.

### 4. Le volume ne sert à rien sans structure

Passer de 4 à 12 articles/mois n'a rien donné tant que les articles n'étaient pas au format V11. Ce n'est pas le volume qui crée le +320 %, c'est le respect du cahier des charges.

### 5. Le suivi manuel des citations LLM est irremplaçable

Aucun outil ne track correctement les citations dans ChatGPT/Claude/Perplexity en avril 2026. Le panel manuel de 50 requêtes/mois prend 2h mais donne des insights qu'aucun dashboard n'offre.

---

## 🔄 Ce qui a changé dans la V11 grâce à Boatcible

Boatcible a directement fait évoluer la méthodologie :

| Constat Boatcible | Modification V11 |
|---|---|
| Réponses FAQ < 50 mots jamais citées | Minimum 50 mots imposé |
| Réponses > 100 mots reformulées par LLM | Maximum 90 mots imposé |
| Schéma Article + WebPage créaient des conflits | Interdits dans V11 (Yoast suffit) |
| Articles sans tableaux moins cités | 2+ tableaux obligatoires |
| CTA en fin d'article ignoré | CTA **avant** la FAQ (visible dans la scroll) |
| 5 H2 insuffisants pour longue traîne | Minimum 7 H2 |

---

## ❓ FAQ

### Ces résultats sont-ils reproductibles sur d'autres secteurs ?

Oui, la méthodologie V11 est agnostique au secteur. Elle a depuis été déployée sur CPEC (plomberie/électricité Cannes) et DCM Avocats (droit, Cannes) avec des premiers signaux positifs dans les 6 semaines. Les amplitudes varient selon la concurrence du secteur : un secteur de niche comme le nautique haut de gamme permet des gains plus rapides qu'un secteur saturé.

### Combien d'articles faut-il pour voir des résultats ?

Le cas Boatcible a nécessité environ **40 articles V11** publiés sur 5 mois pour atteindre +320 %. Les premiers signaux apparaissent à partir de 10-15 articles pilier bien maillés. En dessous, l'autorité topique est insuffisante pour faire bouger les positions de façon significative.

### Peut-on faire la même chose sans n8n ?

Techniquement oui, mais le pipeline automatisé change l'économie du projet. Sans automatisation, produire 12 articles V11 par mois coûte environ 3 à 5 fois plus cher en temps humain. L'automatisation rend le modèle **299 € HT/mois** viable.

### Pourquoi "vente directe chantier" et pas "vente directe usine" ?

C'est le vocabulaire du secteur nautique. "Usine" évoque la production de masse, "chantier naval" désigne les constructeurs italiens artisanaux (BWA, BMA, Marshall). Le respect du lexique métier est un signal E-E-A-T fort pour Google et un critère de citabilité LLM.

### Les citations LLM génèrent-elles du trafic réel ?

Oui, mais de façon difficile à attribuer. Les outils d'analytics ne tracent pas les visites issues de ChatGPT avec précision (souvent classées en "direct" ou "referral" obscur). Boatcible constate une hausse de **38 %** du trafic "direct" depuis les pages profondes — cohérent avec des utilisateurs ayant copié-collé une URL citée par un LLM.

### Qu'est-ce qui a le plus contribué aux +320 % ?

Par ordre décroissant d'impact estimé :

1. La structure V11 des articles (≈ 40 % de l'effet)
2. Le maillage en cocons sémantiques (≈ 25 %)
3. Les schémas JSON-LD propres (≈ 15 %)
4. Le volume et la régularité de publication (≈ 10 %)
5. Les optimisations techniques (perf, robots.txt) (≈ 10 %)

### Le modèle est-il défendable face à Google Updates ?

Les Core Updates Google de septembre et novembre 2025 ont été passés **sans perte de positions**. La raison probable : la V11 est alignée sur ce que Google valorise structurellement (E-E-A-T, réponses claires, expertise démontrée), pas sur des hacks techniques. Un site qui respecte la V11 survit aux updates parce qu'il ne dépend pas d'une faille algorithmique.

### Boatcible va-t-il continuer à servir de labo ?

Oui. Le site reste le premier terrain d'expérimentation pour chaque nouvelle itération (V12, V13…) avant déploiement chez les clients. C'est ce qui garantit que HDVMA ne vend jamais une méthode non testée sur son propre actif.

---

## 📖 Méthodologie & sources

- [Search Console — Boatcible.com](https://search.google.com/search-console) (données internes)
- [Google Analytics 4](https://analytics.google.com) (données internes)
- Ahrefs — audit mots-clés (accès payant)
- Panel manuel 50 requêtes / mois — ChatGPT, Claude, Perplexity
- [`methodologie.md`](methodologie.md) — Le détail du pipeline V11

---

## 🎯 Pour aller plus loin

- [`methodologie.md`](methodologie.md) — Le cahier des charges V11 complet
- [`geo-vs-seo.md`](geo-vs-seo.md) — Pourquoi le GEO change la donne
- [Boatcible.com](https://boatcible.com) — Le site réel
- [hdvma.fr](https://hdvma.fr) — Pour appliquer la méthode sur votre site

Questions sur le cas Boatcible ? Contact direct : [cire@hdvma.com](mailto:cire@hdvma.com)

---

*Cas client Boatcible — © HDVMA 2026 — Licence CC BY 4.0.*
