# 2026 - ECE - Ing4 - Fin - IA Probabiliste, Theorie des Jeux et Machine Learning - Groupe X

Projet pedagogique d'exploration des approches d'intelligence artificielle probabiliste, de la theorie des jeux et du machine learning pour les etudiants de l'ECE.

---

## Modalites du projet

### Echeances importantes
- **17-18 mars 2026** : Presentation des sujets proposes
- **24-25 mars** : Checkpoint intermediaire (CM ML)
- **29 mars** : Deadline de soumission des projets par Pull Request sur ce depot
- **31 mars - 1er avril** : Presentation finale et rendu

### Date de livraison
Le code avec le README devront etre livres dans un sous-dossier de ce depot pour chaque groupe 2 jours au plus tard avant la presentation.

### Taille des groupes
La taille standard d'un groupe est de **3 personnes**.
- Groupes de 2 : tolere (+1 point bonus potentiel pour la charge)
- Groupes de 4 : tolere (-1 point malus potentiel pour la dilution)
- Individuel : exceptionnel (+3 points bonus potentiel)

### Evaluation collegiale
L'evaluation portera sur :
1. **Presentation/Communication** : Clarte, pedagogie, qualite des slides
2. **Contenu theorique** : Comprehension des enjeux, etat de l'art, contexte
3. **Contenu technique** : Qualite du code, resultats obtenus, demos
4. **Organisation/Collaboration** : Activite Git, repartition du travail

### Livrables attendus
- **Code source** propre et documente
- **README** complet (contexte, installation, usage, resultats)
- **Slides** de la presentation (PDF ou lien)

### Instructions de soumission

#### IMPORTANT : Organisation du travail

> **ATTENTION** : Tout votre travail **DOIT** etre organise dans un **sous-repertoire dedie** a votre groupe.
>
> **Structure obligatoire** :
> ```
> /groupe-XX-nom-sujet/
> |-- README.md          # Documentation de votre projet
> |-- src/               # Code source
> |-- docs/              # Documentation technique
> |-- slides/            # Support de presentation (PDF ou lien)
> |-- ...
> ```
>
> Ne pas mettre vos fichiers a la racine du depot.
> Tout doit etre dans votre sous-repertoire de groupe.

#### Soumission du code et de la documentation
1. **Creer un fork** de ce depot sur votre compte GitHub (vous n'avez pas les droits d'ecriture sur ce depot)
2. **Creer un sous-repertoire** pour votre groupe : `groupe-XX-nom-sujet/` (ex: `groupe-03-portfolio-bayesien/`)
3. **Developper votre projet** exclusivement dans ce sous-repertoire
4. **Soumettre une Pull Request** vers ce depot **au moins 2 jours avant la presentation** (soit le **29 mars 2026** au plus tard)
5. La PR doit inclure :
   - Le code source complet et fonctionnel dans votre sous-repertoire
   - Un README detaille dans votre sous-repertoire (installation, utilisation, tests)
   - La documentation technique

#### Soumission du support de presentation
- Les slides de presentation doivent etre soumises **avant le debut de la presentation** (soit le **31 mars 2026** au matin)
- Format accepte : PDF, PowerPoint, ou lien vers Google Slides/Canva
- Ajouter les slides dans votre sous-repertoire (`groupe-XX/slides/`) ou partager le lien dans le README de votre sous-repertoire

#### Checklist de soumission
- [ ] Fork du depot cree
- [ ] Sous-repertoire `groupe-XX-nom-sujet/` cree avec tout le contenu dedans
- [ ] README avec procedure d'installation et tests dans le sous-repertoire
- [ ] Pull Request creee et reviewable
- [ ] Slides de presentation soumises (dans le sous-repertoire ou lien dans README)
- [ ] Tous les membres du groupe identifies dans la PR (noms + GitHub usernames)

---

## Sujets detailles pour le projet

Vous etes libres de choisir l'un des sujets ci-dessous ou de proposer un sujet personnel (a faire valider par les encadrants).
**Technologie libre** : Python (recommande pour l'ecosysteme ML), C#/.NET (historique du cours), C++, Julia, etc.

---

### Categorie 1 : IA Probabiliste et Modeles Graphiques

Ces sujets explorent l'incertitude, l'inference bayesienne et la modelisation statistique. Ils demandent une bonne comprehension des distributions de probabilites et des graphes de facteurs.

#### 1.1. TrueSkill et Matchmaking (Competition)
Le classement de joueurs dans les jeux en ligne (Xbox Live, LoL, Chess) est un probleme probabiliste complexe. Au-dela du simple systeme ELO, le systeme TrueSkill utilise des graphes de facteurs pour modeliser l'incertitude sur la competence de chaque joueur (une gaussienne avec moyenne et variance).
- **Travail attendu** :
    - Implementer un moteur d'inference (via Expectation Propagation ou Variational Inference) pour mettre a jour les scores apres chaque match.
    - Visualiser la convergence de l'incertitude (sigma) au fil des parties.
- **Extensions** : Gerer les equipes heterogenes, le "draw margin" (probabilite de nul), ou la dynamique temporelle (un joueur progresse ou regresse).
- **Ressources** :
    - [Papier TrueSkill (Microsoft)](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/)
    - [TrueSkill 2 (Papier recent)](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/)
    - [Chapitre du livre MBML](http://mbmlbook.com/TrueSkill.html)

#### 1.2. Inference Causale (Causal Inference)
Correlation n'est pas causalite. Comment savoir si une promo a *cause* une vente ou si c'est juste la saisonnalite ?
- **Objectif** : Estimer l'effet causal moyen (ATE) d'une intervention (politique economique, campagne marketing) a partir de donnees observationnelles.
- **Outils** : Utiliser **Pyro** ou **DoWhy** pour modeliser les contrefactuels.
- **Ressources** :
    - [Tutoriel Causal Inference avec Pyro](https://pyro.ai/examples/intro_long.html)
    - [DoWhy Library](https://microsoft.github.io/dowhy/)

#### 1.3. Marketing Mix Modeling (MMM) Bayesien
Un sujet tres demande en entreprise : optimiser le budget pub.
- **Probleme** : Attribuer les ventes aux differents canaux (TV, Facebook, Google) sachant qu'il y a des effets de saturation (rendements decroissants) et de delai (Adstock).
- **Approche** : Utiliser **PyMC** pour construire un modele hierarchique qui estime ces parametres inconnus.
- **Ressources** :
    - [PyMC-Marketing](https://github.com/pymc-labs/pymc-marketing)
    - [Google LightweightMMM](https://github.com/google/lightweight_mmm)

#### 1.4. Bayesian Sports Analytics
Predire les resultats sportifs mieux que les bookmakers.
- **Objectif** : Modeliser la force des equipes (attaque/defense) dans un championnat (Foot, NBA) en prenant en compte l'avantage du terrain.
- **Technique** : Modeles hierarchiques sous **Stan** (via CmdStanPy ou RStan).
- **Ressources** :
    - [Stan Case Studies: Sports](https://mc-stan.org/users/documentation/case-studies.html)
    - [Baio & Blangiardo (2010) - Hierarchical model for Serie A](https://discovery.ucl.ac.uk/id/eprint/16040/1/16040.pdf)

#### 1.5. Bayesian Neural Networks (BNNs)
Le pont entre le Deep Learning et les Probabilites.
- **Concept** : Au lieu d'avoir des poids fixes, chaque poids du reseau de neurones est une distribution de probabilite. Cela permet au reseau de dire "je ne sais pas" (incertitude epistemique).
- **Travail attendu** : Implementer un BNN simple sous **Pyro** ou **TyXe** pour la classification d'images et visualiser l'incertitude sur des exemples hors distribution (OOD).
- **Ressources** : [TyXe (Pyro BNNs)](https://github.com/cifkao/tyxe), [Tutoriel Pyro BNN](https://pyro.ai/examples/bnn.html).

#### 1.6. Modeles Probabilistes Modernes (Pyro / Gaussian Processes)
Explorez les frameworks probabilistes modernes sous Python qui combinent Deep Learning et Probabilites.
- **Sujet A : Rational Speech Acts (RSA)** - Modeliser la pragmatique du langage : comment un locuteur choisit ses mots pour etre compris, et comment un auditeur interprete l'ambiguite (ironie, hyperbole). Utiliser le framework **Pyro** pour simuler ces agents recursifs.
    - [Tutoriel Pyro RSA](https://pyro.ai/examples/RSA-implicature.html)
- **Sujet B : Processus Gaussiens (Gaussian Processes)** - Une methode puissante pour la regression non-parametrique, offrant une estimation de l'incertitude "gratuite". Ideal pour les donnees financieres ou temporelles. Utiliser **GPyTorch** pour passer a l'echelle sur GPU.
    - [Deep Kernel Learning](https://arxiv.org/abs/1511.02222)

---

### Categorie 2 : Theorie des Jeux et Systemes Multi-Agents

Ces sujets traitent de la prise de decision strategique, de la cooperation et de la competition entre agents autonomes.

#### 2.1. Poker AI et Information Imparfaite
Le Poker est le "drosophile" de l'IA en information imparfaite (on ne voit pas les cartes de l'adversaire). C'est un probleme bien plus dur que les Echecs ou le Go.
- **Technique cle** : **Counterfactual Regret Minimization (CFR)**. L'agent apprend en minimisant son "regret" d'avoir joue une action plutot qu'une autre a posteriori.
- **Travail attendu** :
    - Implementer un algorithme CFR (ou MCCFR) sur une version simplifiee du Poker (Leduc Hold'em ou Kuhn Poker).
    - Analyser la strategie obtenue (Nash Equilibrium).
- **Ressources** :
    - [OpenSpiel (DeepMind)](https://github.com/deepmind/open_spiel)
    - [Libratus](https://science.sciencemag.org/content/359/6374/418) et [Pluribus](https://science.sciencemag.org/content/365/6456/885)

#### 2.2. Hanabi AI : Cooperation et Theory of Mind
Hanabi est un jeu de cartes cooperatif unique ou l'on voit les cartes des autres mais pas les siennes. Il faut communiquer des indices limites.
- **Defi** : L'agent doit modeliser ce que les autres savent ("Theory of Mind") et interpreter les indices comme des signaux implicites.
- **Travail attendu** : Entrainer un agent RL (ex: Rainbow DQN ou PPO) capable de jouer avec des humains ou d'autres bots.
- **Ressources** :
    - [Hanabi Learning Environment](https://github.com/deepmind/hanabi-learning-environment)
    - [The Hanabi Challenge (Papier)](https://arxiv.org/abs/1902.00506)

#### 2.3. Mean Field Games (Jeux a Champ Moyen)
Comment modeliser l'interaction strategique d'une foule immense (ex: traders sur un marche, banc de poissons) ?
- **Concept** : Au lieu de modeliser N agents, on modelise un agent representatif face a une "distribution moyenne" des autres.
- **Approche ML** : Utiliser des reseaux de neurones (Neural ODEs) pour resoudre les equations differentielles stochastiques couplees (Hamilton-Jacobi-Bellman + Fokker-Planck).
- **Ressources** : [Mean Field Games & ML (Papier)](https://arxiv.org/abs/2003.06069), [Tutoriel MFG](https://github.com/Nathan-Sanglier/M2MO-Mean-Field-Games)

#### 2.4. Deep Learning for Mechanism Design (Encheres)
Concevoir des regles economiques (encheres) optimales pour maximiser le revenu, via le Deep Learning ("Differentiable Economics").
- **Probleme** : Concevoir une enchere multi-objets optimale est mathematiquement impossible analytiquement.
- **Solution** : Entrainer un reseau de neurones (RegretNet) qui prend en entree les valorisations des acheteurs et sort les allocations et les prix, en maximisant le revenu sous contrainte d'incitation (IC).
- **Ressources** : [Optimal Auctions through Deep Learning](https://arxiv.org/abs/1905.05533), [GitHub RegretNet](https://github.com/srp3/regretnet)

#### 2.5. Theorie des Jeux Evolutionniste et Finance
La theorie des jeux ne sert pas qu'a jouer, elle modelise aussi les dynamiques de marche.
- **Sujet A : Dynamiques de marche** - Modeliser la concurrence entre strategies de trading (trend-following vs mean-reversion vs random) comme une population d'agents en competition evolutionniste. Simuler les dynamiques de type "Hawk-Dove" dans un marche financier.
- **Sujet B : Echange de reins (Kidney Exchange)** - Organiser des chaines d'echanges croises pour sauver le maximum de vies. Probleme d'optimisation combinatoire et de theorie des jeux cooperatifs.
    - [Travaux de Tuomas Sandholm](http://www.cs.cmu.edu/~sandholm/)

---

### Categorie 3 : Machine Learning Avance et Deep Learning

Sujets exigeants necessitant une rigueur methodologique (gestion des donnees, metriques, validation).

#### 3.1. Trading Algorithmique et Finance Quantitative
La finance quantitative est un terrain de jeu ideal pour les series temporelles et le RL.
- **Plateforme** : Utiliser **[QuantConnect](https://www.quantconnect.com/)** (moteur LEAN). Plateforme professionnelle permettant de backtester des strategies en Python/C# sur des donnees historiques de haute qualite.
- **Sujets possibles** :
    - **Strategie Alpha** : Creer un algo qui bat le marche (S&P500) sur 5 ans
    - **GANs in Finance** : Utiliser des GANs (TimeGAN) pour generer des donnees synthetiques de marche
    - **Sentiment Analysis** : Trader en fonction des news financieres (NLP sur titres de presse)

#### 3.2. NLP Avance : Analyse de Sentiment Financier et Fake News
Le traitement du langage naturel (NLP) applique a la finance et l'information.
- **Sujet A : Sentiment de marche** - Analyser le sentiment des rapports financiers, tweets et news pour predire les mouvements de marche. Detecter les signaux faibles dans les communications des PDG (earnings calls).
- **Sujet B : Detection de Fake News financieres** - Classifier les articles financiers comme fiables ou manipulatoires (pump & dump, FUD). Utiliser BERT/RoBERTa fine-tune sur des donnees financieres.
- **Outils** : [HuggingFace Transformers](https://huggingface.co/transformers/), [FinBERT](https://github.com/ProsusAI/finBERT)

#### 3.3. Reinforcement Learning : Trading et Controle
Apprendre par essai-erreur dans un environnement dynamique.
- **Sujet A : RL pour le trading** - Entrainer un agent RL a gerer un portefeuille (decisions buy/sell/hold) en maximisant le Sharpe ratio sur des donnees historiques.
- **Sujet B : Controle de jeux** - Apprendre a un agent a jouer a un jeu video (Snake, Mario, Doom) ou a controler un systeme physique (pendule inverse).
- **Algos** : Comparer PPO, DQN et SAC.
- **Lib** : [Stable-Baselines3](https://github.com/DLR-RM/stable-baselines3), [Gymnasium](https://gymnasium.farama.org/)

---

### Categorie 4 : Confidentialite et ML (Privacy Preserving ML)

Comment entrainer des modeles sans voir les donnees ? Sujet critique pour la banque et l'assurance (RGPD).

#### 4.1. Chiffrement Homomorphe
Le Saint Graal de la privacy : effectuer des calculs (inference ML) directement sur des donnees chiffrees, sans jamais les dechiffrer.
- **Travail attendu** : Utiliser une librairie specialisee pour entrainer un modele simple (Regression, Arbre de decision) qui peut predire sur des donnees chiffrees.
- **Application finance** : Scoring de credit sur donnees bancaires chiffrees.
- **Ressources** :
    - [Microsoft SEAL](https://github.com/Microsoft/SEAL)
    - [Concrete ML (Zama)](https://github.com/zama-ai/concrete-ml) : Convertir des modeles Scikit-learn en equivalents chiffres

#### 4.2. Federated Learning (Apprentissage Federe)
Entrainer un modele global sur des donnees decentralisees (ex: succursales bancaires, hopitaux) sans jamais centraliser les donnees brutes.
- **Concept** : Le modele voyage vers les donnees, apprend localement, et renvoie uniquement les mises a jour de poids (gradients) au serveur central.
- **Application finance** : Detection de fraude multi-banques sans partage de donnees clients.
- **Ressources** : [TensorFlow Federated](https://www.tensorflow.org/federated), [PySyft](https://github.com/OpenMined/PySyft)

---

### Categorie 5 : Recherche et Innovation

Sujets exploratoires bases sur des publications recentes (NeurIPS, ICML). Pour les etudiants qui veulent toucher a la recherche.

#### 5.1. GFlowNets (Generative Flow Networks)
Une nouvelle famille de modeles generatifs probabilistes (introduite par Yoshua Bengio) concue pour echantillonner des objets composites (molecules, graphes, portefeuilles) proportionnellement a une recompense.
- **Application finance** : Generer des portefeuilles diversifies proportionnellement a leur rendement ajuste au risque.
- **Travail attendu** : Implementer un GFlowNet simple sur un environnement de grille ou de generation de portefeuilles.
- **Ressources** : [Tutoriel GFlowNet (Mila)](https://mila.quebec/fr/article/gflownet-tutorial), [TorchGFN Library](https://github.com/GFNOrg/torchgfn)

#### 5.2. Conformal Prediction (Quantification d'Incertitude)
Comment garantir qu'une prediction est "sure" ? La prediction conforme permet de generer des intervalles de confiance valides mathematiquement, quel que soit le modele sous-jacent.
- **Application finance** : Transformer les predictions de prix en intervalles garantis (ex: "Le prix sera entre 10EUR et 12EUR avec 95% de certitude").
- **Travail attendu** : Prendre un modele "boite noire" et utiliser la prediction conforme pour generer des intervalles fiables sur des donnees financieres.
- **Ressources** : [MAPIE (Library Python)](https://github.com/scikit-learn-contrib/MAPIE), [Awesome Conformal Prediction](https://github.com/valeman/awesome-conformal-prediction)

---

### Categorie 6 : Applications Concretes et Finance

Sujets appliques directement au monde de la finance et de l'entreprise.

#### 6.1. Optimisation de Portefeuille avec Modeles Probabilistes
Au-dela de la theorie de Markowitz classique, utiliser des modeles bayesiens pour l'allocation d'actifs.
- **Probleme** : L'optimisation mean-variance classique est tres sensible aux erreurs d'estimation. Les approches bayesiennes (Black-Litterman, shrinkage estimators) permettent d'integrer des priors et de regulariser les estimations.
- **Travail attendu** :
    - Implementer le modele Black-Litterman avec des "views" probabilistes
    - Comparer avec Markowitz classique sur des donnees reelles (Yahoo Finance)
    - Visualiser les frontiere efficientes et les allocations
- **Ressources** :
    - [PyPortfolioOpt](https://github.com/robertmartin8/PyPortfolioOpt)
    - [Riskfolio-Lib](https://github.com/dcajasn/Riskfolio-Lib)

#### 6.2. Credit Scoring avec IA Explicable (XAI)
Le scoring de credit est un cas d'usage majeur du ML en finance, avec des contraintes reglementaires fortes (explicabilite RGPD).
- **Probleme** : Un modele de credit doit etre a la fois precis ET explicable. Un client refuse a le droit de savoir pourquoi.
- **Travail attendu** :
    - Entrainer un modele de scoring (XGBoost, LightGBM) sur un dataset public (German Credit, Lending Club)
    - Appliquer des methodes d'explicabilite : SHAP, LIME, counterfactual explanations
    - Analyser les biais potentiels (age, genre, origine)
- **Ressources** :
    - [SHAP Library](https://github.com/slundberg/shap)
    - [InterpretML](https://github.com/interpretml/interpret)

#### 6.3. Detection de Fraude en Temps Reel
La detection de fraude est un probleme de classification fortement desequilibre avec des contraintes de latence.
- **Probleme** : Moins de 0.1% des transactions sont frauduleuses. Comment detecter ces anomalies sans generer trop de faux positifs ?
- **Travail attendu** :
    - Implementer et comparer des approches : Isolation Forest, Autoencoders, GNN sur graphes de transactions
    - Gerer le desequilibre (SMOTE, class weights, focal loss)
    - Evaluer avec des metriques adaptees (AUPRC, F1, cout financier)
- **Ressources** :
    - [Kaggle Credit Card Fraud Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)
    - [PyOD (Outlier Detection)](https://github.com/yzhao062/pyod)

---

## Ressources Generales

- **HuggingFace** : Pour les modeles et datasets (NLP, CV, Audio)
- **Kaggle** : Pour trouver des datasets propres et des notebooks d'exemple
- **PapersWithCode** : Pour trouver l'etat de l'art sur une tache donnee
- **ArXiv** : Pour les papiers de recherche originaux
- **QuantConnect** : Plateforme de backtesting algorithmique (gratuite pour la recherche)
- **Yahoo Finance / yfinance** : Donnees financieres historiques gratuites
