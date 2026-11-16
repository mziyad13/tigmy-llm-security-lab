# Tigmy : laboratoire de sécurité d'un assistant IA local

Tigmy est un assistant IA de service client que je construis étape par étape autour d'un modèle open source exécuté en local. L'objectif est de reproduire les étapes qu'une entreprise suit pour déployer son propre assistant IA, puis de **l'attaquer à chaque étape** pour identifier ses failles et les corriger.

> Projet personnel à but pédagogique, réalisé dans le cadre de ma 3e année en cybersécurité. Toutes les données utilisées sont fictives.

## Méthodologie

Chaque étape suit le même cycle :

1. **Construire** une nouvelle brique de l'assistant
2. **Attaquer** cette brique (injection de prompt, fuite de données, abus d'outils…)
3. **Corriger** les failles trouvées
4. **Vérifier** que les correctifs fonctionnent

Les attaques sont classées selon l'[OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/).

## Feuille de route

- [ ] **Étape 1 : Modèle et prompt système.** Exécuter un modèle open source en local avec Ollama et l'interroger via son API. Définir l'identité de Tigmy et ses règles avec un prompt système.
- [ ] **Étape 2 : RAG (Retrieval-Augmented Generation).** Découper la documentation de l'entreprise, la transformer en embeddings, la stocker dans une base vectorielle et retrouver les bons passages pour chaque question, afin que Tigmy s'appuie sur les vraies règles au lieu d'inventer.
- [ ] **Étape 3 : Appel d'outils.** Donner à Tigmy des outils (suivi de commande, création de ticket…) pour en faire un agent, puis les exposer via MCP (Model Context Protocol).
- [ ] **Étape 4 : Contrôle d'accès par rôle.** Associer chaque requête à un utilisateur et à son rôle, pour que Tigmy n'accède qu'aux données autorisées pour la personne en face.
- [ ] **Étape 5 : Garde-fous.** Filtrer les entrées, détecter les tentatives d'injection et masquer les données personnelles dans les réponses.
- [ ] **Étape 6 : Observabilité et évaluations.** Tracer chaque appel d'outil, journaliser les prompts et automatiser une suite de tests d'attaque exécutée avant chaque modification.
- [ ] **Bonus : Cache et routage.** Mettre en cache les questions fréquentes et router les questions simples vers un modèle plus léger, en vérifiant que le cache ne divulgue pas de réponses d'un utilisateur à un autre.

## Technologies

- Ubuntu (WSL2)
- Python
- Ollama avec un modèle open source (Qwen / Llama)

## Résultats

Le rapport des attaques et des correctifs sera publié ici au fil du projet.
