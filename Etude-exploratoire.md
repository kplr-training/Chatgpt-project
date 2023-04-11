## Projet ChatGPT

## Définition : 

**ChatGPT** est un modèle de langage développé par OpenAI basé sur l'architecture **GPT-3.5**. Il est capable de comprendre et de produire du texte dans de nombreuses langues, 
en utilisant une vaste base de connaissances et une puissante intelligence artificielle pour générer des réponses aux questions et aux requêtes des utilisateurs. 

ChatGPT est souvent utilisé comme assistant virtuel pour fournir des informations, des réponses ou des suggestions sur de nombreux sujets.

## GPT-3.5 : 

**GPT-3.5** est une extension de l'architecture de base de GPT-3, qui est un modèle de langage basé sur des réseaux de neurones profonds, spécifiquement un Trans-former. 

Le Transformer est une architecture de réseau de neurones profonds utilisée pour traiter le langage naturel. 

C'est une amélioration par rapport aux réseaux de neurones traditionnels, qui utili-sent des réseaux de neurones récurrents (RNN) ou des réseaux de neurones con-volutifs (CNN) pour la modélisation du langage.
Le Transformer utilise une approche de traitement du langage naturel basée sur l'attention pour apprendre des représentations sémantiques de mots et de phrases.

Plus précisément, l'architecture de GPT-3.5 comprend des blocs de transformer qui sont empilés les uns sur les autres pour former un réseau de neurones pro-fond. 

Chaque bloc de transformer comporte plusieurs couches de traitement, compre-nant notamment des couches d'attention multi-têtes, des couches de normalisa-tion, des couches de positionnement, des couches entièrement connectées et des couches de sortie.

GPT-3.5 est conçu pour apprendre à prédire la probabilité de chaque mot dans une séquence donnée, en fonction du contexte. Il peut ainsi générer du texte en continu à partir d'un début de phrase donné, ou répondre à des questions en produisant des réponses appropriées.

## GPT : 
L'architecture de ChatGPT est basée sur le modèle de traitement de langage natu-rel (NLP) GPT (Generative Pre-trained Transformer).

Le modèle de traitement de langage naturel GPT (Generative Pre-trained Trans-former) est un réseau de neurones profond de type Transformer, utilisé pour la modélisation du langage naturel. Il a été développé par OpenAI et est considéré comme l'un des modèles de langage les plus performants à ce jour. 

GPT est un modèle de langage pré-entraîné, ce qui signifie qu'il est entraîné sur de grandes quantités de données textuelles non étiquetées avant d'être affiné pour une tâche spécifique. Cela permet au modèle de capturer les caractéristiques gé-nérales du langage et d'apprendre à générer du texte de manière fluide et cohé-rente.

Le modèle GPT fonctionne en utilisant un mécanisme d'attention, qui permet d'identifier les parties importantes d'une séquence en fonction du contexte, et une technique de génération de texte appelée "beam search", qui permet de générer du texte en prenant en compte plusieurs hypothèses à chaque étape.

## Caractéristiques de l'architecture de ChatGPT :

Parmi les principales caractéristiques de l'architecture de ChatGPT, on trouve :

- Couches de Transformers :
L'architecture de ChatGPT utilise plusieurs couches de Transformers pour encoder les données d'entrée et générer les prédictions de sortie. Chaque couche de transformer est composée d'un module d'attention qui permet de pondérer les différentes parties de l'entrée en fonction de leur impor-tance.

-	Entraînement supervisé :
ChatGPT est pré-entraîné sur des tâches de modélisation de langage, ce qui lui permet de capturer des informations sémantiques et syntaxiques sur la langue. 
Le modèle est ensuite fine-tuné sur une tâche spécifique, par exemple la génération de texte pour un chatbot.

-	Génération de texte :
ChatGPT utilise une méthode de génération de texte basée sur un proces-sus de décision probabiliste.
Le modèle évalue la probabilité de chaque mot possible dans la séquence de sortie en fonction de la séquence d'en-trée et des connaissances préalables acquises lors de l'entraînement.
 
-	Réponse conversationnelle :
ChatGPT peut être utilisé pour la réponse conversationnelle, en utilisant une séquence de texte d'entrée pour générer une séquence de texte de sortie. 
Le modèle est entraîné pour prédire la réponse la plus appropriée à une question donnée ou à une entrée de conversation.
L'architecture de ChatGPT utilise des transformers pour encoder l'entrée et géné-rer une séquence de texte de sortie en utilisant un processus de génération pro-babiliste. 
Le modèle est entraîné sur des tâches de modélisation de langage naturel pour acquérir des connaissances sur la langue, puis fine-tuné sur des tâches spéci-fiques, telles que la réponse conversationnelle dans le cas d'un chatbot.

## Architecture de ChatGPT : 
![image](https://user-images.githubusercontent.com/123748177/231160175-081bb647-f38b-4187-b381-8f1a038ea644.png)

-	ChatGPT a été affiné à partir d'un modèle de la série GPT-3.5, qui a terminé son entraînement début 2022. 
-	ChatGPT et GPT-3.5 ont été entraînés sur une infrastructure de super calcul Azure AI. 

 
## Architecture de GPT-3 : 
 
L'architecture de GPT-3 est très similaire à celle de GPT-2, mais avec plusieurs améliorations significatives.

![image](https://user-images.githubusercontent.com/123748177/231160265-ce425266-12ba-491a-a137-99b1ac2b7b41.png)

On peut décrire d’une manière générale de l'architec-ture de GPT-3 comme suit:

-	Couche d'embedding d'entrée : 
Le texte d'entrée est d'abord encodé en vecteurs denses à l'aide d'une couche d'embedding d'entrée.

-	N couches de transformer : 
GPT-3 utilise un total de N couches de transformer. Chaque couche com-prend une sous-couche d'attention multi-têtes, une sous-couche feed-forward, et une couche de normalisation. 
 
-	Couche de positionnement : 
Pour aider le modèle à comprendre la position des différents éléments dans la séquence d'entrée, GPT-3 utilise une couche de positionnement. Cette couche ajoute une représentation de la position à l'embedding de chaque token.
-	Couche de normalisation : 
Après les N couches de transformer, GPT-3 utilise une couche de normalisa-tion finale pour normaliser les sorties.
-	Couche de sortie : 
La couche de sortie finale génère une distribution de probabilité sur le vo-cabulaire, ce qui permet de générer du texte. La sortie de cette couche est souvent utilisée pour des tâches telles que la classification de texte ou la gé-nération de texte.

## Entrainement de ChatGPT

ChatGPT a été entraîné en utilisant l'apprentissage par renforcement à partir de commentaires humains (RLHF), une technique qui combine l'apprentissage super-visé avec l'apprentissage par renforcement. 

ChatGPT a été entraîné en suivant la procédure suivante :

•	Fine-tuning supervisé :
 
  -	Le modèle initial a été entraîné en utilisant le fine-tuning supervisé. Des entraîneurs d'IA humains ont fourni des conversations dans les-quelles ils ont joué les deux côtés - l'utilisateur et un assistant d'IA. 
  
  -	Ils ont eu accès à des suggestions générées par le modèle pour les aider à composer leurs réponses. 
  
  -	Ce jeu de données a été mélangé avec l'ensemble de données Ins-tructGPT, qui a été transformé en un format de dialogue.

•	Collecte de données pour l'apprentissage par renforcement : 

-	Pour créer un modèle de récompense pour l'apprentissage par renforcement, des données de comparaison ont été collectées. 
-	Les conversations que les entraîneurs d'IA ont eues avec le chatbot ont été utilisées. 
-	Un message généré par le modèle a été sélectionné au hasard, et plusieurs complétions alternatives ont été échantillonnées, puis les entraîneurs d'IA les ont classées.

•	Entraînement par apprentissage par renforcement : 
Le modèle a été finement ajusté en utilisant l'algorithme Proximal Policy Optimization à l'aide du modèle de récompense. Ce processus a été répété plusieurs fois.

•	Formation supplémentaire : 
Après l'entraînement par renforcement, le modèle a été encore entraîné sur un grand corpus de données de conversation.

Dans l'ensemble, la technique RLHF permet au modèle d'apprendre à partir des commentaires humains d'une manière qui équilibre le compromis entre exploration et exploitation. 
Cette approche a conduit à un modèle capable de générer des réponses plus naturelles et engageantes dans une conversation.


## Notions importantes : 

**1.	NLP**

Le NLP, ou Traitement du Langage Naturel en français, est une branche de l'intelligence artificielle (IA) qui se focalise sur la compréhension et la manipulation du langage humain par les machines. 

Le NLP vise à permettre aux machines de comprendre, d'interpréter, d'analyser et de générer du texte de manière similaire à la manière dont le font les humains.

Les étapes principales du NLP comprennent généralement les suivantes :

-	Acquisition et prétraitement des données : 
Cette étape implique la collecte des données textuelles nécessaires pour l'analyse, qu'il s'agisse de textes bruts ou de données structurées. 
Les données peuvent être collectées à partir de diverses sources, telles que des sites web, des bases de données, ou des documents.

-	Tokenization : 
Cette étape consiste à diviser le texte en unités plus petites appelées "tokens". Les tokens peuvent être des mots individuels, des phrases, des pa-ragraphes ou d'autres unités, en fonction des besoins spécifiques de l'ap-plication.

-	Nettoyage et normalisation des données : 
Cela implique le nettoyage du texte en supprimant les caractères indési-rables, la ponctuation, les chiffres, les espaces inutiles, ainsi que la normali-sation des mots en les mettant en minuscules ou en les lemmatisant (réduire les mots à leur forme de base).

-	Analyse linguistique : 
Cette étape vise à comprendre la structure grammaticale et sémantique du texte. Elle peut inclure des tâches telles que l'analyse morphologique (ex-traction des préfixes, suffixes, etc.), l'analyse syntaxique (analyse des rela-tions grammaticales entre les mots), et l'analyse sémantique (extraction du sens des mots et des phrases).

-	Extraction d'information : 
Cette étape consiste à extraire des informations spécifiques du texte, telles que les entités nommées (noms de personnes, d'organisations, etc.), les re-lations entre les entités, ou les concepts clés.

-	Traitement du texte : 
Cela peut inclure diverses tâches telles que la classification de texte (attri-buer des catégories à des textes), l'analyse de sentiment (déterminer les émotions ou les opinions exprimées dans un texte), ou la génération de texte (création de texte par la machine).

-	Évaluation et amélioration : 
Cette étape consiste à évaluer les performances du modèle de NLP et à l'améliorer en ajustant les paramètres du modèle, en utilisant des tech-niques d'apprentissage supervisé ou non supervisé, et en itérant sur les étapes précédentes en fonction des résultats obtenus.

On peut résumer le pipeline de Traitement du Langage Naturel comme suit :

 ![image](https://user-images.githubusercontent.com/123748177/231162324-e569baa6-e1b8-41bb-8c3e-a20a779652d3.png)

**2.	RLHF**

L'apprentissage par renforcement à partir de commentaires humains (RLHF) est une approche d'apprentissage automatique qui combine des éléments de l'ap-prentissage par renforcement et de l'apprentissage supervisé. 

Dans le contexte de l'intelligence artificielle, l'apprentissage par renforcement est un paradigme d'apprentissage où un agent apprend à prendre des décisions en interagissant avec un environnement pour maximiser une récompense cumulative. 

L'apprentissage supervisé, quant à lui, consiste à entraîner un modèle en lui four-nissant des exemples annotés avec des étiquettes de sortie souhaitées.

Dans le cadre du RLHF, les commentaires humains sont utilisés pour fournir des informations de supervision supplémentaires à l'agent d'apprentissage par renfor-cement. 

Les commentaires humains peuvent prendre la forme d'évaluations, de notations ou de critiques de l'agent ou de ses actions. Ces commentaires sont utilisés pour ajuster le comportement de l'agent en lui fournissant des signaux d'apprentissage supplémentaires, ce qui permet d'améliorer ses performances.

Le RLHF est souvent utilisé dans des scénarios où il peut être difficile ou coûteux de déterminer des récompenses ou des étiquettes de supervision pour les actions de l'agent de manière automatisée. 

En incorporant les commentaires humains dans le processus d'apprentissage par renforcement, le RLHF vise à améliorer l'efficacité et la performance de l'agent d'apprentissage automatique en exploitant les connaissances et les jugements des experts humains.

On peut résumer le process de l'apprentissage par renforcement à partir de com-mentaires humains (RLHF) comme suit :

![image](https://user-images.githubusercontent.com/123748177/231162471-8b2d3b4a-ea1d-419f-ae0c-63a3d515c15a.png)

 
**3.	PPO**

L'algorithme Proximal Policy Optimization (PPO) est une méthode d'apprentissage par renforcement (RL) utilisée pour entraîner des modèles d'IA à prendre des déci-sions en prenant en compte un environnement et en maximisant une récompense cumulée dans cet environnement. 

L'algorithme PPO est largement utilisé pour entraîner des agents d'IA dans des domaines tels que les jeux, la robotique, la finance, et d'autres applications où les décisions doivent être prises de manière séquentielle en fonction de l'état de l'en-vironnement.

C’est une approche basée sur la politique (policy-based) de l'apprentissage par renforcement, ce qui signifie qu'il apprend directement une politique, c'est-à-dire une fonction qui mappe les états de l'environnement aux actions à prendre. 

Contrairement aux méthodes basées sur la valeur (value-based) qui estiment la valeur des actions ou des états, les méthodes basées sur la politique visent à ap-prendre directement la meilleure action à prendre dans un état donné.

Cet algorithme utilise une approche d'optimisation proximale pour mettre à jour la politique de manière itérative. Il prend en compte la probabilité de choisir une ac-tion donnée sous la politique actuelle, et utilise cette probabilité pour ajuster les mises à jour de la politique afin qu'elles restent dans une "zone proximale" autour de la politique actuelle. 

Cela permet de garantir que les mises à jour de la politique sont stables et qu'elles ne divergent pas trop de la politique actuelle, évitant ainsi les oscillations indési-rables et les mises à jour trop agressives.

Il est également conçu pour être parallélisable et efficace en termes de calcul, ce qui le rend approprié pour l'entraînement de modèles d'IA sur de grandes quanti-tés de données.

Il a été largement utilisé avec succès dans de nombreuses applications d'IA, et il existe plusieurs variantes et améliorations de l'algorithme de base PPO, telles que PPO-Clip et PPO-Penalty, qui permettent de mieux adapter l'algorithme aux be-soins spécifiques des projets d'apprentissage par renforcement.


## Limites de ChatGPT :

ChatGPT présente plusieurs limitations, notamment :

•	Parfois, le modèle écrit des réponses plausibles mais incorrectes ou sans aucun sens. Corriger ce problème est difficile, car :

-	Lors de l'entraînement RL, il n'y a actuellement pas de source de vérité 
-	Entraîner le modèle à être plus prudent l'amène à décliner des questions qu'il pourrait répondre correctement 
-	Et l'entraînement supervisé induit en erreur le modèle car la réponse idéale dépend de ce que le modèle sait plutôt que de ce que le démonstrateur humain sait.

•	ChatGPT est sensible aux modifications de la formulation de la question ou aux tentatives de la même demande plusieurs fois. 

•	Le modèle est souvent excessivement verbeux et utilise souvent certaines expressions de manière répétitive.

•	Idéalement, le modèle poserait des questions de clarification lorsque l'utilisateur fournit une requête ambiguë. Au lieu de cela, nos modèles actuels devinent souvent ce que l'utilisateur a voulu dire.

•	Bien que des efforts en ayant faites pour faire en sorte que le modèle refuse les demandes inappropriées, il arrive parfois qu'il réponde à des instructions nuisibles ou manifeste un comportement biaisé. 

## Outils de mise en place de ChatGPT :

ChatGPT est construit et entraîné en utilisant une combinaison d'outils et de technologies, notamment :

•	Python : 
 
-	Python est un langage de programmation largement utilisé pour les tâches d'apprentissage automatique et d'apprentissage profond en raison de sa simplicité, de ses bibliothèques étendues pour le calcul scientifique et de son large soutien communautaire. 
-	Python est utilisé pour implémenter la logique de base de ChatGPT, notamment le traitement des données, l'architecture du modèle et le pipeline d'entraînement.

•	PyTorch : 
 
-	PyTorch est un framework d'apprentissage profond open source, développé par le laboratoire de recherche en intelligence artificielle de Facebook .

-	Il offre des outils efficaces pour la construction et l'entraînement de réseaux de neurones, ce qui le rend adapté au développement de modèles d'apprentissage automatique complexes comme ChatGPT. 

-	PyTorch est utilisé pour implémenter l'architecture du réseau de neu-rones de ChatGPT, ainsi que pour l'entraînement du modèle en utili-sant différentes techniques d'optimisation.

•	Bibliothèques d'apprentissage par renforcement : 
 
-	ChatGPT, en tant que modèle d'IA entraîné à l'aide de l'apprentis-sage par renforcement, peut utiliser des bibliothèques spécialisées pour l'apprentissage par renforcement, telles que OpenAI Gym, Stable-Baselines ou RLlib.

-	Ces bibliothèques fournissent des environnements, des algorithmes et des utilitaires pré-implémentés pour l'entraînement et l'évaluation de modèles d'apprentissage par renforcement.
 
•	Bibliothèques de traitement des données : 

-	ChatGPT peut également utiliser des bibliothèques de traitement des données en Python, telles que NumPy, Pandas ou NLTK, pour des tâches telles que la préparation des données, la tokenisation du texte et l'ingénierie des caractéristiques. 

-	Ces bibliothèques fournissent des outils puissants pour la manipula-tion des données, qui sont essentiels pour la préparation des don-nées d'entrée pour l'entraînement du modèle.

•	Plateformes de cloud computing : 

-	L'entraînement de modèles à grande échelle comme ChatGPT peut nécessiter des ressources de calcul importantes. 

-	Des plateformes de cloud computing telles que Amazon Web Ser-vices (AWS), Google Cloud Platform (GCP) ou Microsoft Azure peu-vent être utilisées pour provisionner des machines virtuelles, des GPUs ou des TPUs pour l'entraînement du modèle de manière distri-buée et scalable.

•	Autres bibliothèques et outils : 
-	Selon les exigences spécifiques et les détails de mise en œuvre, ChatGPT peut également utiliser d'autres bibliothèques et outils pour des tâches telles que l'évaluation du modèle, l'optimisation des hy-perparamètres, le déploiement du modèle et la surveillance. 

-	Des exemples de tels outils incluent scikit-learn, TensorFlow, PyTorch Lightning et Docker.
-	
Il est important de noter que les outils et les technologies exacts utilisés pour cons-truire et entraîner ChatGPT peuvent évoluer avec le temps à mesure que de nouvelles technologies émergent et que les meilleures pratiques évoluent.
