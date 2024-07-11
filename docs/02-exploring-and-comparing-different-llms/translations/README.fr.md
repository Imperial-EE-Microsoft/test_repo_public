# Exploration et comparaison de différents LLM

[![Exploration et comparaison de différents LLM](./images/02-lesson-banner.png?WT.mc_id=academic-105485-koreyst)](https://learn.microsoft.com/_themes/docs.theme/master/en-us/_themes/global/video-embed.html?id=39aa0f98-826a-4f71-a24d-e888a8e80246?WT.mc_id=academic-105485-koreyst)

> *Cliquez sur l'image ci-dessus pour visionner la vidéo de cette leçon.*

Avec la leçon précédente, nous avons vu comment l'IA générative change le paysage technologique, comment les grands modèles de langage (LLMs) fonctionnent et comment une entreprise - comme notre start-up - peut les appliquer à ses cas d'utilisation et se développer ! Dans ce chapitre, nous cherchons à comparer et à contraster différents types de grands modèles de langage (LLMs) pour comprendre leurs avantages et inconvénients.

La prochaine étape du parcours de notre start-up est d'explorer le paysage actuel des LLMs et de comprendre lesquels conviennent à notre cas d'utilisation.

## Introduction

Cette leçon couvrira :

- Différents types de LLMs dans le paysage actuel.
- Tester, itérer et comparer différents modèles pour votre cas d'utilisation dans Azure.
- Comment déployer un LLM.

## Objectifs d'apprentissage

Après avoir terminé cette leçon, vous serez capable de :

- Sélectionner le bon modèle pour votre cas d'utilisation.
- Comprendre comment tester, itérer et améliorer les performances de votre modèle.
- Savoir comment les entreprises déploient des modèles.

## Comprendre les différents types de LLMs

Les LLMs peuvent avoir plusieurs catégories en fonction de leur architecture, de leurs données d'entraînement et de leur cas d'utilisation. Comprendre ces différences aidera notre start-up à sélectionner le bon modèle pour le scénario et à comprendre comment tester, itérer et améliorer les performances.

Il existe de nombreux types différents de modèles LLM, votre choix de modèle dépend de ce que vous souhaitez les utiliser, de vos données, de ce que vous êtes prêt à payer et plus encore.

Selon que vous visez à utiliser les modèles pour la génération de texte, d'audio, de vidéo, d'image, etc., vous pouvez opter pour un type de modèle différent.

- **Reconnaissance audio et vocale**. Pour cette fin, les modèles de type Whisper sont un excellent choix car ils sont polyvalents et destinés à la reconnaissance vocale. Il est entraîné sur des données audio diverses et peut effectuer une reconnaissance vocale multilingue. En savoir plus sur [les modèles Whisper ici](https://platform.openai.com/docs/models/whisper?WT.mc_id=academic-105485-koreyst).

- **Génération d'images**. Pour la génération d'images, DALL-E et Midjourney sont deux choix très connus. DALL-E est proposé par Azure OpenAI. [En savoir plus sur DALL-E ici](https://platform.openai.com/docs/models/dall-e?WT.mc_id=academic-105485-koreyst) et également dans le chapitre 9 de ce programme.

- **Génération de texte**. La plupart des modèles sont entraînés sur la génération de texte et vous avez une grande variété de choix, de GPT-3.5 à GPT-4. Ils ont des coûts différents, GPT-4 étant le plus cher. Il vaut la peine de regarder le [terrain de jeu Azure OpenAI](https://oai.azure.com/portal/playground?WT.mc_id=academic-105485-koreyst) pour évaluer quels modèles conviennent le mieux à vos besoins en termes de capacité et de coût.

- **Multimodalité**. Si vous cherchez à gérer plusieurs types de données en entrée et en sortie, vous voudrez peut-être examiner des modèles comme [gpt-4 turbo with vision ou gpt-4o](https://learn.microsoft.com/azure/ai-services/openai/concepts/models#gpt-4-and-gpt-4-turbo-models?WT.mc_id=academic-105485-koreyst) - les dernières versions des modèles OpenAI - qui sont capables de combiner le traitement du langage naturel à la compréhension visuelle, permettant des interactions via des interfaces multimodales.

Sélectionner un modèle signifie que vous obtenez certaines capacités de base, qui pourraient ne pas être suffisantes. Souvent, vous avez des données spécifiques à l'entreprise que vous devez somehow faire savoir au LLM. Il existe plusieurs choix différents sur la façon d'aborder cela, plus sur cela dans les sections à venir.

### Modèles de base versus LLMs

Le terme modèle de base a été [créé par des chercheurs de Stanford](https://arxiv.org/abs/2108.07258?WT.mc_id=academic-105485-koreyst) et défini comme un modèle d'IA qui suit certains critères, tels que :

- **Ils sont entraînés à l'aide d'un apprentissage non supervisé ou d'un apprentissage auto-supervisé**, ce qui signifie qu'ils sont entraînés sur des données multimodales non étiquetées et qu'ils ne nécessitent pas d'annotation ou d'étiquetage humain des données pour leur processus d'entraînement.
- **Ce sont des modèles très volumineux**, basés sur des réseaux neuronaux très profonds entraînés sur des milliards de paramètres.
- **Ils sont normalement destinés à servir de « base » pour d'autres modèles**, ce qui signifie qu'ils peuvent être utilisés comme point de départ pour la construction d'autres modèles, qui peuvent être faits par fine-tuning.

![Modèles de base versus LLMs](./images/FoundationModel.png?WT.mc_id=academic-105485-koreyst)

Source de l'image : [Guide essentiel des modèles de base et des grands modèles de langage | par Babar M Bhatti | Medium
](https://thebabar.medium.com/essential-guide-to-foundation-models-and-large-language-models-27dab58f7404)

Pour clarifier davantage cette distinction, prenons ChatGPT comme exemple. Pour construire la première version de ChatGPT, un modèle appelé GPT-3.5 a servi de modèle de base. Cela signifie qu'OpenAI a utilisé des données spécifiques au chat pour créer une version ajustée de GPT-3.5 qui était spécialisée dans la réalisation de performances optimales dans des scénarios de conversation, tels que les chatbots.

![Modèle de base](./images/Multimodal.png?WT.mc_id=academic-105485-koreyst)

Source de l'image : [2108.07258.pdf (arxiv.org)](https://arxiv.org/pdf/2108.07258.pdf?WT.mc_id=academic-105485-koreyst)

### Modèles open source versus propriétaires

Une autre façon de catégoriser les LLMs est de savoir s'ils sont open source ou propriétaires.

Les modèles open source sont des modèles mis à la disposition du public et peuvent être utilisés par n'importe qui. Ils sont souvent mis à disposition par la société qui les a créés ou par la communauté de recherche. Ces modèles sont autorisés à être inspectés, modifiés et personnalisés pour les différents cas d'utilisation dans les LLMs. Cependant, ils ne sont pas toujours optimisés pour une utilisation en production et peuvent ne pas être aussi performants que les modèles propriétaires. De plus, le financement des modèles open source peut être limité et ils peuvent ne pas être maintenus à long terme ou ne pas être mis à jour avec les dernières recherches. Des exemples de modèles open source populaires comprennent [Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html?WT.mc_id=academic-105485-koreyst), [Bloom](https://sapling.ai/llm/bloom?WT.mc_id=academic-105485-koreyst) et [LLaMA](https://sapling.ai/llm/llama?WT.mc_id=academic-105485-koreyst).

Les modèles propriétaires sont des modèles qui appartiennent à une entreprise et qui ne sont pas mis à disposition du public. Ces modèles sont souvent optimisés pour une utilisation en production. Cependant, ils ne sont pas autorisés à être inspectés, modifiés ou personnalisés pour différents cas d'utilisation. De plus, ils ne sont pas toujours disponibles gratuitement et peuvent nécessiter un abonnement ou un paiement pour être utilisés. De plus, les utilisateurs n'ont pas le contrôle sur les données utilisées pour entraîner le modèle, ce qui signifie qu'ils doivent confier au propriétaire du modèle l'assurance du respect de la confidentialité des données et de l'utilisation responsable de l'IA. Des exemples de modèles propriétaires populaires comprennent [les modèles OpenAI](https://platform.openai.com/docs/models/overview?WT.mc_id=academic-105485-koreyst), [Google Bard](https://sapling.ai/llm/bard?WT.mc_id=academic-105485-koreyst) ou [Claude 2](https://www.anthropic.com/index/claude-2?WT.mc_id=academic-105485-koreyst).

### Embedding versus génération d'images versus génération de texte et de code

Les LLMs peuvent également être catégorisés par la sortie qu'ils génèrent.

Les embeddings sont un ensemble de modèles qui peuvent convertir du texte en une forme numérique, appelée embedding, qui est une représentation numérique du texte d'entrée. Les embeddings facilitent la compréhension par les machines des relations entre les mots ou les phrases et peuvent être consommés en tant qu'entrées par d'autres modèles, tels que les modèles de classification ou de clustering qui ont de meilleures performances sur les données numériques. Les modèles d'embedding sont souvent utilisés pour le transfert d'apprentissage, où un modèle est construit pour une tâche de substitution pour laquelle il y a une abondance de données, puis les poids du modèle (embeddings) sont réutilisés pour d'autres tâches en aval. Un exemple de cette catégorie est [les embeddings OpenAI](https://platform.openai.com/docs/models/embeddings?WT.mc_id=academic-105485-koreyst).

![Embedding](./images/Embedding.png?WT.mc_id=academic-105485-koreyst)

Les modèles de génération d'images sont des modèles qui génèrent des images. Ces modèles sont souvent utilisés pour l'édition d'images, la synthèse d'images et la traduction d'images. Les modèles de génération d'images sont souvent entraînés sur de grands ensembles de données d'images, tels que [LAION-5B](https://laion.ai/blog/laion-5b/?WT.mc_id=academic-105485-koreyst), et peuvent être utilisés pour générer de nouvelles images ou pour éditer des images existantes avec des techniques d'inpainting, de super-résolution et de colorisation. Les exemples incluent [DALL-E-3](https://openai.com/dall-e-3?WT.mc_id=academic-105485-koreyst) et [les modèles de diffusion stable](https://github.com/Stability-AI/StableDiffusion?WT.mc_id=academic-105485-koreyst).

![Génération d'images](./images/Image.png?WT.mc_id=academic-105485-koreyst)

Les modèles de génération de texte et de code sont des modèles qui génèrent du texte ou du code. Ces modèles sont souvent utilisés pour la synthèse de texte, la traduction et la réponse aux questions. Les modèles de génération de texte sont souvent entraînés sur de grands ensembles de données textuelles, tels que [BookCorpus](https://www.cv-foundation.org/openaccess/content_iccv_2015/html/Zhu_Aligning_Books_and_ICCV_2015_paper.html?WT.mc_id=academic-105485-koreyst), et peuvent être utilisés pour générer du nouveau texte ou pour répondre à des questions. Les modèles de génération de code, comme [CodeParrot](https://huggingface.co/codeparrot?WT.mc_id=academic-105485-koreyst), sont souvent entraînés sur de grands ensembles de données de code, tels que GitHub, et peuvent être utilisés pour générer du nouveau code ou pour corriger des bugs dans du code existant.

 ![Génération de texte et de code](./images/Text.png?WT.mc_id=academic-105485-koreyst)

### Encodeur-décodeur versus décodeur uniquement

Pour parler des différents types d'architectures de LLMs, utilisons une analogie.

Imaginez que votre responsable vous a confié la tâche d'écrire un quiz pour les étudiants. Vous avez deux collègues ; l'un supervise la création du contenu et l'autre supervise la révision.

Le créateur de contenu est comme un modèle de décodeur unique, il peut regarder le sujet et voir ce que vous avez déjà écrit, puis il peut écrire un cours en fonction de cela. Il est très bon pour écrire du contenu engageant et informatif, mais il n'est pas très bon pour comprendre le sujet et les objectifs d'apprentissage. Certains exemples de modèles de décodeur sont les modèles de la famille GPT, tels que GPT-3.

Le réviseur est comme un modèle d'encodeur uniquement, il regarde le cours écrit et les réponses, remarque la relation entre eux et comprend le contexte, mais il n'est pas bon pour générer du contenu. Un exemple de modèle d'encodeur unique serait BERT.

Imaginez que nous pouvons également avoir quelqu'un qui pourrait créer et réviser le quiz, c'est un modèle encodeur-décodeur. Certains exemples seraient BART et T5.

### Service versus modèle

Maintenant, parlons de la différence entre un service et un modèle. Un service est un produit proposé par un fournisseur de services cloud et est souvent une combinaison de modèles, de données et d'autres composants. Un modèle est le composant principal d'un service et est souvent un modèle de base, tel qu'un LLM.

Les services sont souvent optimisés pour une utilisation en production et sont souvent plus faciles à utiliser que les modèles, via une interface utilisateur graphique. Cependant, les services ne sont pas toujours disponibles gratuitement et peuvent nécessiter un abonnement ou un paiement pour être utilisés, en échange de l'utilisation de l'équipement et des ressources du propriétaire du service, optimisant les dépenses et l'évolutivité. Un exemple de service est [le service Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/overview?WT.mc_id=academic-105485-koreyst), qui offre un plan tarifaire pay-as-you-go, ce qui signifie que les utilisateurs sont facturés proportionnellement à leur utilisation du service. De plus, le service Azure OpenAI offre une sécurité de niveau entreprise et un cadre d'IA responsable en plus des capacités des modèles.

Les modèles ne sont que le réseau neuronal, avec les paramètres, les poids et autres. Les entreprises peuvent les exécuter localement, mais elles doivent acheter du matériel, construire une structure pour l'évolutivité et acheter une licence ou utiliser un modèle open source. Un modèle comme LLaMA est disponible à être utilisé, nécessitant une puissance de calcul pour exécuter le modèle.

## Comment tester et itérer avec différents modèles pour comprendre les performances sur Azure

Une fois que notre équipe a exploré le paysage actuel des LLMs et identifié certains bons candidats pour leurs scénarios, la prochaine étape consiste à les tester sur leurs données et leur charge de travail. Il s'agit d'un processus itératif, effectué par des expériences et des mesures.
La plupart des modèles que nous avons mentionnés dans les paragraphes précédents (modèles OpenAI, modèles open source comme Llama2 et Hugging Face transformers) sont disponibles dans le [Catalogue de modèles](https://learn.microsoft.com/azure/ai-studio/how-to/model-catalog-overview?WT.mc_id=academic-105485-koreyst) dans [Azure AI Studio](https://ai.azure.com/?WT.mc_id=academic-105485-koreyst).

[Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/what-is-ai-studio?WT.mc_id=academic-105485-koreyst) est une plate-forme cloud conçue pour les développeurs pour construire des applications d'IA générative et gérer l'ensemble du cycle de développement - de l'expérimentation à l'évaluation - en combinant tous les services d'IA Azure dans un seul hub avec une interface graphique pratique. Le catalogue de modèles dans Azure AI Studio permet à l'utilisateur de :

- Trouver le modèle de base qui l'intéresse dans le catalogue - propriétaire ou open source, en filtrant par tâche, licence ou nom. Pour améliorer la recherche, les modèles sont organisés en collections, comme la collection Azure OpenAI, la collection Hugging Face, et plus encore.

![Catalogue de modèles](./images/AzureAIStudioModelCatalog.png?WT.mc_id=academic-105485-koreyst)

- Examiner la carte du modèle, y compris une description détaillée de l'utilisation prévue et des données d'entraînement, des exemples de code et des résultats d'évaluation sur la bibliothèque d'évaluations internes.

![Carte du modèle](./images/ModelCard.png?WT.mc_id=
Pour répondre aux attentes de l'utilisateur, la réponse sera adaptée. Dans ce cas, on parle d'apprentissage « one-shot » si la demande ne comprend qu'un seul exemple et d'apprentissage « few shot » s'il comprend plusieurs exemples. L'ingénierie de la demande avec contexte est l'approche la plus rentable pour commencer. ### Génération augmentée de récupération (RAG) Les LLM (modèles de langage basés sur les transformers) ont pour limite qu'ils ne peuvent utiliser que les données qui ont été utilisées pendant leur formation pour générer une réponse. Cela signifie qu'ils ne connaissent rien des faits qui se sont produits après leur processus de formation et qu'ils ne peuvent pas accéder aux informations non publiques (comme les données de l'entreprise). Cela peut être surmonté grâce à RAG, une technique qui augmente la demande avec des données externes sous forme de fragments de documents, en tenant compte des limites de longueur de la demande. Cela est soutenu par des outils de base de données vectorielles (comme [Azure Vector Search](https://learn.microsoft.com/azure/search/vector-search-overview?WT.mc_id=academic-105485-koreyst)) qui récupèrent les fragments utiles de sources de données prédéfinies variées et les ajoutent au contexte de la demande. Cette technique est très utile lorsqu'une entreprise n'a pas suffisamment de données, de temps ou de ressources pour affiner un LLM, mais souhaite toujours améliorer les performances sur une charge de travail spécifique et réduire les risques de fabrications, c'est-à-dire la mystification de la réalité ou le contenu nuisible. ### Modèle affiné L'affinage est un processus qui exploite le transfert d'apprentissage pour « adapter » le modèle à une tâche en aval ou pour résoudre un problème spécifique. Contrairement à l'apprentissage few-shot et à RAG, cela entraîne la génération d'un nouveau modèle, avec des poids et des biais mis à jour. Il nécessite un ensemble d'exemples d'entraînement composé d'une entrée unique (la demande) et de sa sortie associée (la complétion). Cela serait l'approche préférée si : - **Utilisation de modèles affinés**. Une entreprise souhaite utiliser des modèles d'incorporation moins performants (comme les modèles d'incorporation) plutôt que des modèles haute performance, ce qui donne une solution plus rentable et plus rapide. - **Considération de la latence**. La latence est importante pour un cas d'utilisation spécifique, il n'est donc pas possible d'utiliser des demandes très longues ou le nombre d'exemples qui doivent être appris à partir du modèle ne correspond pas à la limite de longueur de la demande. - **Rester à jour**. Une entreprise dispose de nombreuses données de haute qualité et d'étiquettes de vérité terrain et des ressources nécessaires pour maintenir ces données à jour au fil du temps. ### Modèle entraîné Former un LLM à partir de zéro est sans aucun doute l'approche la plus difficile et la plus complexe à adopter, nécessitant des quantités massives de données, des ressources qualifiées et une puissance de calcul appropriée. Cette option ne doit être envisagée que dans un scénario où une entreprise dispose d'un cas d'utilisation spécifique au domaine et d'une grande quantité de données centrées sur le domaine. ## Vérification des connaissances Quelle pourrait être une bonne approche pour améliorer les résultats de complétion LLM ? 1. Ingénierie de la demande avec contexte 2. RAG 3. Modèle affiné R: 3, si vous avez le temps, les ressources et des données de haute qualité, l'affinage est la meilleure option pour rester à jour. Cependant, si vous cherchez à améliorer les choses et que vous manquez de temps, il vaut la peine de considérer RAG en premier. ## 🚀 Défi Renseignez-vous davantage sur la façon dont vous pouvez [utiliser RAG](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview?WT.mc_id=academic-105485-koreyst) pour votre entreprise. ## Excellent travail, continuez votre apprentissage Après avoir terminé cette leçon, consultez notre [collection d'apprentissage de l'IA générative](https://aka.ms/genai-collection?WT.mc_id=academic-105485-koreyst) pour continuer à améliorer vos connaissances en matière d'IA générative ! Passez à la leçon 3 où nous verrons comment [construire avec l'IA générative de manière responsable](../03-using-generative-ai-responsibly/README.md?WT.mc_id=academic-105485-koreyst) !


Avertissement: La traduction a été effectuée à partir d'un modèle d'IA et peut ne pas être parfaite. Veuillez examiner le résultat et apporter les corrections nécessaires.