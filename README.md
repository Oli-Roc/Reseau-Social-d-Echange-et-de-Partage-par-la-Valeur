# 🔄 Graphe d'Échange Cyclique Capacitaire (GECC)

> **La monnaie est un lien, pas un bien. La valeur se conserve dans la circulation, pas dans l'accumulation.**
> — *Théorie de l'Échange Juste, Rocca (2024)*

[![Licence](https://img.shields.io/badge/licence-open%20source%20copyleft-brightgreen)](LICENSE)
[![Statut](https://img.shields.io/badge/statut-actif-success)]()
[![Protocole](https://img.shields.io/badge/protocole-SECC%20v1.0-blue)]()
[![Fondement](https://img.shields.io/badge/fondement-théorie%20des%20graphes-orange)]()
[![Compatible](https://img.shields.io/badge/compatible-PCG%20%7C%20IFRS%20%7C%20US%20GAAP-lightgrey)]()

---

## 🧭 En une phrase

Le GECC est un **système de compensation économique multilatérale décentralisé**, fondé sur la théorie mathématique des graphes orientés, qui permet à n'importe quel groupe d'agents d'organiser leurs échanges de valeur **sans intermédiaire monétaire**, **sans dette**, **sans exclusion**, à toute échelle.

---

## ⚡ Le problème que nous résolvons

Les systèmes monétaires existants — des devises fiat aux cryptomonnaies — reproduisent trois pathologies structurelles :

| Pathologie | Mécanisme | Impact |
|---|---|---|
| **Concentration** | La monnaie-bien s'accumule (r > g) | Les riches peuvent échanger, les autres non |
| **Exclusion** | L'accès dépend de la solvabilité | 1,4 milliard de personnes non bancarisées |
| **Destruction** | La dette génère des intérêts qui n'ont jamais été créés | Endettement structurel et crises en cascade |

Ces pathologies ne sont pas des accidents — elles sont des **propriétés intrinsèques** d'un instrument monétaire traité comme un bien privatif et accumulable.

Le GECC change l'instrument, pas les agents.

---

## 🔬 Comment ça marche — la rupture mathématique

### Le graphe comme monnaie

Le GECC représente l'économie sous la forme d'un **graphe orienté pondéré** `G = (V, E)` où :
- **V** = ensemble des agents (nœuds)
- **E** = arêtes de compatibilité transactionnelle orientées
- **w(i→j)** = valeur de la transaction en unité de compte

Chaque échange potentiel est une arête. Chaque cycle fermé `A → B → C → A` est une **compensation multilatérale automatique**.

### La transformation centrale — de NP-difficile à polynomial

> Le problème de coordination économique multilatérale est NP-difficile dans sa formulation générale (Karp, 1972).

Sous trois contraintes structurelles simples, il devient **un programme linéaire résolu en temps polynomial O(n × e × log n)** :

```
Maximiser  Σ f(i→j)    ← valeur totale compensée

Sous :
  Σ f_ji − Σ f_ij = 0   ∀ i   ← conservation des flux (Kirchhoff)
  0 ≤ f_ij ≤ x_ij       ∀ (i,j) ← capacités bornées
  |S_i| ≤ L_i            ∀ i   ← plafonds de solde
```

*Algorithme : Successive Shortest Paths (Klein, 1967)*

### Les trois contraintes qui font tout

| Contrainte | Formule | Signification |
|---|---|---|
| **Balance équilibrée** | `Σ f_entrants = Σ f_sortants` ∀ agent | Ce qu'on reçoit = ce qu'on donne |
| **Capacités égales** | `Σ f_ij ≤ κ × V̄_groupe` ∀ agent | Même capacité d'accès pour tous |
| **Multi-connectivité** | `deg(v) ≥ 3`, `f_ij ≤ X% × C` | Réseau dense et résilient |

**Résultat :** avec `k_eff = 3` connexions effectives par agent, **99,97 % des agents** sont inclus dans la même composante fortement connexe (Erdős & Rényi, 1960).

---

## 💰 L'argument économique

### Réduction du besoin en fonds de roulement

Un réseau de 20 entreprises échangeant 100 000 € / mois :

```
Système classique :  chaque entreprise immobilise 10 000–20 000 € de trésorerie
Avec le GECC :       τ = 80% → chaque entreprise n'a besoin que de 1 000–2 000 € de provision

Économie de trésorerie : -85 à -90 %
```

### La provision de couverture — la seule liquidité nécessaire

```
P_i = β × V^prog_i       avec β ∈ [10 %, 20 %]
```

`β` est **dynamique et auto-calibrant** : il diminue quand le réseau compense bien, augmente quand il compense moins bien. Aucune décision discrétionnaire requise.

### Les plafonds de solde asymétriques

```
Plafond de créance :   S_i ≤ α × V^prog_i   (α ∈ 30–50 %)
Plafond de dette :     S_i ≥ −β × V^prog_i  (β ∈ 10–20 %)
```

L'asymétrie reflète la différence réelle de risque entre excès de créances (compensable) et excès de dettes (risque de non-couverture).

### Indicateurs de performance cibles

| Indicateur | Formule | Seuil d'alerte | Cible maturité |
|---|---|---|---|
| Taux de compensation τ | Valeur compensée / Valeur déclarée | τ < 0,60 | τ > 0,85 |
| Degré effectif k_eff | Σ deg(i) / n | k_eff < ln(n) | k_eff ≥ 6 |
| Gini des soldes | Coeff. Gini sur soldes nets | > 0,40 | < 0,25 |
| Ratio de couverture | Σ provisions / Σ dettes brutes | < β_cible | ≥ β_cible |

---

## 🌱 L'argument écologique

### Le Donut intégré dans le graphe

Le GECC intègre nativement la **théorie du Donut de Kate Raworth** sous forme de contraintes vectorielles :

```
∀ i :      Σ Réceptions(i) ≥ σ_i          ← plancher social (vie digne garantie)
∀ (i,j) :  ε(f_ij) ≤ ε_max                ← plafond écologique (limite planétaire)
```

Un échange n'est **valide dans le GECC** que s'il respecte **simultanément** ces deux contraintes. La transition écologique cesse d'être un objectif déclaratif — elle devient une **contrainte structurelle de chaque transaction**.

### La pondération carbone

```
x_ij_effectif = x_ij × (1 − ω_ij)     avec ω_ij ∈ [0 ; 1] selon l'intensité carbone
```

Les transactions à forte empreinte voient leur capacité effective réduite automatiquement. Les échanges durables sont favorisés **par la structure du système**, pas par la volonté individuelle.

### Les biens privés vers les biens communs — une trajectoire programmée

```
Bien privé → Bien de club → Bien commun → Bien public
```

Cette trajectoire est **explicitement programmée** dans les paramètres d'allocation du moteur de cycles. Un agent qui mutualise un bien accède à un plafond de créance majoré de 20–30 %. La durabilité est **économiquement incitée**.

---

## 🤝 L'argument social

### L'accès conditionné à la capacité productive réelle

Dans le GECC, la condition d'entrée dans le système passe de :
- ❌ la **solvabilité préalable** (système classique)
- ✅ la **capacité productive réelle déclarée** (GECC)

Un paysan, un artisan, une association, une communauté sans accès bancaire peuvent participer **à égalité** avec une PME ou une collectivité territoriale.

### L'égalité des capacités transactionnelles

La propriété mathématique fondamentale : **un graphe à capacités égales** présente un potentiel connectif structurellement supérieur à un graphe à capacités inégales. L'égalité des droits d'accès n'est pas un compromis — c'est **une optimisation**.

### Les huit principes d'Ostrom — transposés dans le graphe

La gestion des biens communs dans le GECC respecte les huit principes d'Ostrom (1990) :

1. Définition claire des limites du bien commun
2. Règles d'usage adaptées au contexte local
3. Participation collective à la décision
4. Surveillance effective par le registre du graphe
5. Sanctions graduées (réduction des plafonds)
6. Mécanismes de résolution des conflits
7. Reconnaissance par les autorités extérieures
8. Articulation avec les systèmes réglementaires existants

---

## ⚖️ L'argument juridique et politique

### Nature juridique précise

Le GECC n'est **pas une monnaie** au sens de l'article L.111-1 du Code monétaire et financier. C'est une **convention de compensation multilatérale de créances** :

```
Régime applicable :
  → Art. 1347 Code civil (compensation multilatérale)
  → Directive 2002/47/CE (accords de garantie financière / netting)
  → Directive 2011/7/UE (retards de paiement)
```

**Aucune autorisation réglementaire spécifique n'est requise pour déployer le GECC.**

### Structures juridiques hôtes

| Structure | Échelle | Avantages |
|---|---|---|
| Association loi 1901 | Locale → nationale | Souplesse, objet large |
| SCOP / SCIC | Locale → régionale | Gouvernance démocratique, aides ESS |
| GIE | Régionale → nationale | B2B, réduction BFR inter-entreprises |
| Collectivité territoriale | Territoriale | CGCT, fonds publics, légitimité |
| DAO | Globale | Smart contracts, automatisation |
| Registre informel | Locale, pays émergents | Zéro capital initial |

### La gouvernance décentralisée à trois niveaux

```
Niveau micro  →  Assemblée des agents (50–150 personnes, limite de Dunbar)
                  Paramètres locaux, validation des profils, requalification des biens

Niveau méso   →  Conseil de coordination (délégués élus)
                  Cycles dominants, connexions inter-communautaires

Niveau macro  →  Comité de protocole
                  Maintenance algorithmique, représentation institutionnelle
```

**Principe fondamental :** l'algorithme d'optimisation est **indépendant de la gouvernance politique**. La gouvernance fixe les paramètres — elle ne peut pas intervenir dans le résultat du calcul.

---

## 📐 Architecture technique

### Stack recommandée par phase

| Phase | Participants | Outil | Capacité |
|---|---|---|---|
| 0 — Papier | ≤ 30 | Cahier + réunion physique | Pays émergents, rural |
| 1 — Tableur | 30–100 | Excel/LibreOffice + macro | PME, associations |
| 2 — Application web | 100–5 000 | Python/JS + BDD + interface | Coopératives, filières |
| 3 — Registre distribué | Illimité | Blockchain / smart contracts + API | International |

### Compatibilité comptable

Le GECC est compatible avec **tous les systèmes comptables existants** (PCG, IFRS, US GAAP).

```
Créance initiale :      Débit 411 Clients  /  Crédit 706 Prestations
Dette initiale :        Débit 601 Achats   /  Crédit 401 Fournisseurs
Compensation cyclique : Débit 401          /  Crédit 411  [valeur f(C)]
Provision :             Débit 512 Banque   /  Crédit 4585 Provisions GECC
```

### Scalabilité

La décomposition hiérarchique garantit la scalabilité à toute échelle :

```
Complexité totale : O(n/c × T_local)
  où c = taille des communautés (50–150)
→ Tractable sur matériel ordinaire, quelle que soit la taille du réseau
```

---

## 🚀 Feuille de route de déploiement

### Phase 1 — Amorçage `[0–6 mois | 10–50 participants]`

```yaml
structure:   Association loi 1901 ou convention informelle
beta:        0.15
tau_cible:   0.70
plafond:     0.5 × V̄_groupe
fenetre:     mensuelle
outil:       registre papier ou tableur
objectif:    identifier les 5–10 cycles récurrents
succes:      τ > 0.60 au 6e mois
```

### Phase 2 — Croissance `[6–24 mois | 50–500 participants]`

```yaml
structure:   SCOP ou SCIC
beta:        dynamique (auto-calibrant)
fenetre:     hebdomadaire
outil:       application web + algorithme d'optimisation
objectif:    k_eff > ln(n), premiers cycles dominants
succes:      τ > 0.75, ≥ 3 cycles dominants
```

### Phase 3 — Maturité `[après 24 mois | +500 participants]`

```yaml
structure:   SCIC multi-parties ou DAO
protocole:   complet (planchers sociaux + plafonds écologiques)
outil:       plateforme distribuée, API ouverte, temps réel
objectif:    autonomie et scalabilité complètes
succes:      τ > 0.85, ≥ 1 projet collectif financé par cycles
```

---

## 🌍 Applications sectorielles

### Filières agricoles et alimentaires
> Maraîchers × mécaniciens × transporteurs × restaurateurs → cycles courts à haute valeur compensable. Taux de compensation atteignable : **70–90 %** pour 30–50 participants.

### Transition écologique
> Valorisation économique des échanges invisibles dans le PIB classique : réparation, services de proximité, rénovation énergétique, gestion collective de ressources renouvelables.

### Territoires et collectivités
> La collectivité participe en tant qu'agent du réseau. Cadre légal : art. L.1511-1 CGCT, programme LEADER (fonds FEADER), conventions art. 1347 Code civil.

### Filières industrielles et B2B
> Réduction des délais de paiement, baisse du BFR proportionnelle à τ, renforcement de la résilience de la chaîne d'approvisionnement contre les défaillances en cascade.

### Pays en développement
> **Protocole minimal viable :** un registre (cahier), une fenêtre (réunion périodique), une provision (engagement oral). Compatible avec tontines, coopératives villageoises, associations de producteurs.

---

## 📚 Fondements théoriques

### Mathématiques des graphes et optimisation
- Minty, G.J. (1960) — Théorème de décomposition des circulations
- Ford & Fulkerson (1956) — Théorème flot max / coupe min
- Klein, M. (1967) — Successive Shortest Paths (algorithme central)
- Erdős & Rényi (1960) — Transition de phase et composante géante
- Karp, R.M. (1972) — Complexité NP-difficile de la couverture par cycles

### Économie institutionnelle et théorie des communs
- Ostrom, E. (1990) — *Governing the Commons*
- Samuelson, P.A. (1954) — Classification des biens publics
- Raworth, K. (2017) — *Doughnut Economics*
- Piketty, T. (2013) — *Le Capital au XXIe siècle*
- Axelrod, R. (1984) — *The Evolution of Cooperation*

### Sources fondatrices du GECC
- **Rocca, O. (2024)** — *La Théorie de l'Échange Juste, Tome 1 : Théorie et Principes.* Document open source, copyleft. 161 pages.
- **Protocole SECC** — Cadre normatif, opérationnel et institutionnel complet pour le déploiement du Système d'Échange Cyclique Compensatoire.

---

## 🔐 Éthique et engagements

Le GECC repose sur quatre engagements fondamentaux :

1. **Non-exclusion** — Aucun agent n'est exclu sur la base de sa richesse, nationalité ou statut social.
2. **Transparence radicale** — Tous les paramètres, résultats et décisions de gouvernance sont publics en temps réel.
3. **Non-destruction** — Les biens échangés sont gérés selon les principes de durabilité et de renouvellement (abolition de l'*abusus* pour les biens communs et publics).
4. **Réciprocité** — Tout agent qui reçoit s'engage à contribuer en retour dans les limites de ses capacités.

---

## 📄 Licence

**Document open source — Copyleft — Libre de reproduction avec mention des auteurs.**

Toute organisation déployant le GECC est invitée à partager ses résultats d'expérimentation avec la communauté des utilisateurs.

*Citation requise :* Rocca, O. (2024). *La Théorie de l'Échange Juste.* Document open source. | *Graphe d'Échange Cyclique Capacitaire — corpus théorique complet.*

---

## 🤝 Contribuer

Les contributions sont bienvenues sur tous les aspects du projet :

- **Implémentations algorithmiques** (Python, Rust, JavaScript)
- **Interfaces de gouvernance** (applications web, mobile)
- **Smart contracts** (Ethereum, Substrate, Cosmos)
- **Retours d'expérimentation** terrain (filières, coopératives, territoires)
- **Traductions** et adaptations culturelles

---

*"Deux règles locales simples suffisent à rendre le problème global de coordination calculable de façon optimale sans coordinateur central."*
*— Protocole SECC, Chapitre III*
