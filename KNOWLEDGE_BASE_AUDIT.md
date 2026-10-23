# Audit de la mémoire issue de l’export ChatGPT

Date de l’audit : 2026-10-22  
Statut : audit initial; les chiffres décrivent les fichiers d’extraction retrouvés, pas une mémoire déjà chargée dans le runtime.

## 1. Fichiers retrouvés

Les artefacts d’extraction disponibles dans la bibliothèque ChatGPT sont :

- `ORION_Analyse_Export_ChatGPT_v0_1.xlsx`
- `ORION_MEMORY_v0_5_AUDIT.xlsx`
- `ORION_WORKFLOW_DATASET_v1_2.xlsx`
- `ORION_GITHUB_CONTROLLED_v2_2.xlsx`

Le fichier ZIP original complet n’a pas été confirmé dans la liste des fichiers consultables pendant cet audit. Il n’est donc pas nécessaire de recommencer l’extraction à ce stade; il faut d’abord exploiter et contrôler les artefacts existants.

## 2. Chiffres de l’inventaire

Le fichier d’analyse rapporte 114 conversations :
- ORION / IA : 39
- Création de contenu : 35
- GK Holding / stratégie : 13
- Finance personnelle : 12
- Applications / logiciels : 8
- Rédaction / littérature : 2
- Projets d’affaires : 2
- Autres : 2
- Immigration / Canada : 1

Le fichier d’audit mémoire rapporte :
- 114 conversations analysées;
- 450 candidats mémoire uniques;
- 5 décisions candidates;
- répartition des candidats : ORION 22, CONTENT 62, GK_HOLDING 0, FINANCE 15, APPLICATIONS 8, PROJECTS 2, OTHER 5.

Les deux fichiers utilisent des regroupements différents. Il faut conserver les chiffres tels qu’ils sont fournis et réconcilier les méthodes de classement avant de comparer leurs catégories.

## 3. Diagnostic principal

Le problème prioritaire n’est pas l’absence de données extraites, mais l’écart entre l’extraction et une mémoire d’entreprise validée et utilisable.

Le chiffre `GK_HOLDING = 0` dans l’audit mémoire est un signal important : les décisions de groupe, la structure du holding, les relations entre projets, les priorités et les horizons temporels ne sont pas suffisamment représentés dans cette classification.

Les 450 candidats ne sont pas automatiquement des faits confirmés. Ils doivent être classés en :
- décision explicitement validée;
- fait durable issu d’une source;
- préférence de travail;
- état de projet daté;
- hypothèse ou proposition;
- information contradictoire ou à confirmer.

## 4. Organisation cible

La base documentaire doit distinguer :
1. `01_ARCHIVE` — sources originales conservées sans modification;
2. `02_INDEX` — date, titre, catégorie, projet et mots-clés;
3. `03_KNOWLEDGE` — connaissances durables et règles;
4. `04_DECISIONS` — décisions validées du groupe;
5. `05_CONTENT` — système éditorial et contenus;
6. `06_PROJECTS` — fiches projet, statut, propriétaire, objectifs, risques et prochaines actions;
7. `07_ORION` — charte, architecture et procédures de l’agent;
8. `08_EVALUATION` — tests de compréhension et de sécurité;
9. `09_VERSIONS` — versions de la base, changelog et historique.

## 5. Prochaines étapes recommandées

- Contrôler les feuilles et les lignes des classeurs existants; ne pas régénérer les 114 conversations sans raison.
- Construire une fiche GK HOLDING et une fiche par projet actif à partir des informations explicitement étayées.
- Importer les décisions avec source, date et niveau de confiance; isoler les contradictions.
- Définir un format structuré lisible par machine (Markdown + JSON/YAML si utile) avec identifiants stables.
- Relier la recherche mémoire à l’orchestrateur ORION-TEST et vérifier que l’agent consulte réellement ces fichiers au moment de répondre.
- Créer des tests de questions-réponses fondés sur les projets, les décisions et les règles de sécurité.
- Mesurer la précision des réponses et la capacité à retrouver les sources avant d’augmenter l’autonomie.

## 6. Critère d’acceptation

La mémoire n’est considérée comme intégrée que si un test exécuté dans le runtime montre qu’ORION peut retrouver une décision et une fiche projet pertinentes, citer la source interne utilisée, distinguer un fait validé d’une hypothèse et respecter les permissions d’action.
