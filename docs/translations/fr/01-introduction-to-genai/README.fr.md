# Introduction à l'IA générative et aux grands modèles de langage

[![Introduction à l'IA générative et aux grands modèles de langage](./images/01-lesson-banner.png?WT.mc_id=academic-105485-koreyst)](https://learn.microsoft.com/_themes/docs.theme/master/en-us/_themes/global/video-embed.html?id=36c6795a-e63c-46dd-8d69-df8bbe6e7bc9?WT.mc_id=academic-105485-koreyst)

*(Cliquez sur l'image ci-dessus pour visionner la vidéo de cette leçon)*

L'IA générative est une intelligence artificielle capable de générer du texte, des images et d'autres types de contenus. Ce qui en fait une technologie fantastique, c'est qu'elle démocratise l'IA, tout le monde peut l'utiliser avec aussi peu qu'une demande de texte, une phrase écrite dans une langue naturelle. Il n'est pas nécessaire d'apprendre un langage comme Java ou SQL pour accomplir quelque chose de valable, tout ce dont vous avez besoin est d'utiliser votre langue, de dire ce que vous voulez et une suggestion d'un modèle d'IA sortira. Les applications et l'impact de cela sont énormes, vous pouvez écrire ou comprendre des rapports, écrire des applications et bien plus encore, le tout en quelques secondes.

Dans ce programme, nous explorerons comment notre start-up utilise l'IA générative pour débloquer de nouveaux scénarios dans le monde de l'éducation et comment nous abordons les défis inévitables liés aux implications sociales de son application et aux limitations technologiques.

## Introduction

Cette leçon couvrira :

* Introduction au scénario commercial : notre idée de start-up et notre mission.
* IA générative et comment nous sommes arrivés au paysage technologique actuel.
* Fonctionnement interne d'un grand modèle de langage.
* Capacités principales et cas d'utilisation pratiques des grands modèles de langage.

## Objectifs d'apprentissage

Après avoir terminé cette leçon, vous comprendrez :

* Ce qu'est l'IA générative et comment les grands modèles de langage fonctionnent.
* Comment vous pouvez exploiter les grands modèles de langage pour différents cas d'utilisation, en mettant l'accent sur les scénarios d'éducation.

## Scénario : notre start-up éducative

L'Intelligence Artificielle Générative (IA) représente le summum de la technologie de l'IA, repoussant les limites de ce qui était autrefois considéré comme impossible. Les modèles d'IA générative ont plusieurs capacités et applications, mais pour ce programme, nous allons explorer comment elle révolutionne l'éducation grâce à une start-up fictive. Nous nous référerons à cette start-up comme *notre start-up*. Notre start-up travaille dans le domaine de l'éducation avec une déclaration de mission ambitieuse :

> *améliorer l'accessibilité à l'apprentissage, à l'échelle mondiale, en garantissant un accès équitable à l'éducation et en offrant des expériences d'apprentissage personnalisées à chaque apprenant, selon ses besoins*.

Notre équipe de start-up est consciente que nous ne pourrons pas atteindre cet objectif sans exploiter l'un des outils les plus puissants de l'époque moderne - les grands modèles de langage (LLM).

On s'attend à ce que l'IA générative révolutionne la façon dont nous apprenons et enseignons aujourd'hui, les étudiants ayant à leur disposition des enseignants virtuels 24 heures sur 24 qui fournissent de vastes quantités d'informations et d'exemples, et les enseignants pouvant utiliser des outils innovants pour évaluer leurs élèves et leur donner des commentaires.

![Cinq jeunes étudiants regardant un moniteur - image de DALLE2](./images/students-by-DALLE2.png?WT.mc_id=academic-105485-koreyst)

Pour commencer, définissons quelques concepts et termes de base que nous utiliserons tout au long du programme.

## Comment avons-nous obtenu l'IA générative ?

Malgré l'extraordinaire *hype* créé ces derniers temps par l'annonce de modèles d'IA générative, cette technologie est en gestation depuis des décennies, les premiers efforts de recherche remontant aux années 60. Nous sommes maintenant à un point où l'IA a des capacités cognitives humaines, comme la conversation, comme le montre par exemple [OpenAI ChatGPT](https://openai.com/chatgpt) ou [Bing Chat](https://www.microsoft.com/edge/features/bing-chat?WT.mc_id=academic-105485-koreyst), qui utilise également un modèle GPT pour la recherche web de Bing.

Revenons un peu en arrière, les tout premiers prototypes d'IA consistaient en des chatbots dactylographiés, reposant sur une base de connaissances extraite d'un groupe d'experts et représentée dans un ordinateur. Les réponses dans la base de connaissances étaient déclenchées par des mots clés apparaissant dans le texte d'entrée.
Cependant, il est rapidement devenu clair que cette approche, utilisant des chatbots dactylographiés, ne se développait pas bien.

### Une approche statistique de l'IA : l'apprentissage automatique

Un tournant est survenu dans les années 90, avec l'application d'une approche statistique à l'analyse de texte. Cela a conduit au développement de nouveaux algorithmes - connus sous le nom d'apprentissage automatique - capables d'apprendre des modèles à partir de données, sans être explicitement programmés. Cette approche permet à une machine de simuler la compréhension du langage humain : un modèle statistique est entraîné sur des paires texte-étiquette, permettant au modèle de classifier un texte d'entrée inconnu avec une étiquette prédéfinie représentant l'intention du message.

### Réseaux neuronaux et assistants virtuels modernes

Plus récemment, l'évolution technologique du matériel, capable de traiter des quantités de données plus importantes et des calculs plus complexes, a encouragé la recherche dans les domaines de l'IA, conduisant au développement d'algorithmes d'apprentissage automatique avancés - appelés réseaux neuronaux ou algorithmes d'apprentissage profond.

Les réseaux neuronaux (et en particulier les réseaux neuronaux récurrents - RNN) ont considérablement amélioré le traitement du langage naturel, permettant la représentation du sens du texte de manière plus significative, valorisant le contexte d'un mot dans une phrase.

C'est la technologie qui a alimenté les assistants virtuels nés dans la première décennie du nouveau siècle, très compétents dans l'interprétation du langage humain, l'identification d'un besoin et l'exécution d'une action pour le satisfaire - comme répondre avec un script prédéfini ou consommer un service tiers.

### Aujourd'hui, l'IA générative

Voilà comment nous sommes arrivés à l'IA générative aujourd'hui, qui peut être considérée comme un sous-ensemble de l'apprentissage profond.

![IA, ML, DL et IA générative](./images/AI-diagram.png?WT.mc_id=academic-105485-koreyst)

Après des décennies de recherche dans le domaine de l'IA, une nouvelle architecture de modèle - appelée *Transformer* - a surmonté les limites des RNN, étant capable de recevoir des séquences de texte beaucoup plus longues en entrée. Les transformateurs sont basés sur le mécanisme d'attention, permettant au modèle de donner différents poids aux entrées qu'il reçoit, "prêtant plus d'attention" là où l'information la plus pertinente est concentrée, indépendamment de leur ordre dans la séquence de texte.

La plupart des modèles d'IA générative récents - également connus sous le nom de grands modèles de langage (LLM), car ils travaillent avec des entrées et des sorties textuelles - sont en effet basés sur cette architecture. Ce qui est intéressant avec ces modèles - entraînés sur une énorme quantité de données non étiquetées provenant de sources diverses telles que des livres, des articles et des sites web - c'est qu'ils peuvent être adaptés à une grande variété de tâches et générer un texte grammaticalement correct avec une ressemblance de créativité. Ainsi, non seulement ont-ils considérablement amélioré la capacité d'une machine à "comprendre" un texte d'entrée, mais ils ont également permis à leur capacité de générer une réponse originale en langage humain.

## Comment fonctionnent les grands modèles de langage ?

Dans le chapitre suivant, nous allons explorer différents types de modèles d'IA générative, mais pour l'instant, regardons comment les grands modèles de langage fonctionnent, en mettant l'accent sur les modèles OpenAI GPT (Generative Pre-trained Transformer).

* **Tokenizer, texte en nombres** : Les grands modèles de langage reçoivent un texte en entrée et génèrent un texte en sortie. Cependant, étant des modèles statistiques, ils fonctionnent beaucoup mieux avec des nombres qu'avec des séquences de texte. C'est pourquoi chaque entrée du modèle est traitée par un tokenizer, avant d'être utilisée par le modèle principal. Un token est un morceau de texte - composé d'un nombre variable de caractères, donc la tâche principale du tokenizer est de diviser l'entrée en un tableau de tokens. Ensuite, chaque token est associé à un index de token, qui est l'encodage entier du morceau de texte d'origine.

![Exemple de tokenisation](./images/tokenizer-example.png?WT.mc_id=academic-105485-koreyst)

* **Prédiction des tokens de sortie** : Étant donné n tokens en entrée (avec un maximum de n variant d'un modèle à l'autre), le modèle est capable de prédire un token en sortie. Ce token est ensuite incorporé à l'entrée de l'itération suivante, selon un modèle de fenêtre en expansion, permettant une meilleure expérience utilisateur pour obtenir une (ou plusieurs) phrase en réponse. Cela explique pourquoi, si vous avez déjà joué avec ChatGPT, vous avez peut-être remarqué qu'il semble parfois s'arrêter au milieu d'une phrase.

* **Processus de sélection, distribution de probabilité** : Le token de sortie est choisi par le modèle en fonction de sa probabilité d'apparition après la séquence de texte actuelle. C'est parce que le modèle prédit une distribution de probabilité sur tous les "prochains tokens" possibles, calculée sur la base de son entraînement. Cependant, ce n'est pas toujours le token avec la probabilité la plus élevée qui est choisi dans la distribution résultante. Un degré d'aléatoire est ajouté à ce choix, de sorte que le modèle agit de manière non déterministe - nous n'obtenons pas la même sortie pour la même entrée. Ce degré d'aléatoire est ajouté pour simuler le processus de la pensée créative et peut être réglé à l'aide d'un paramètre de modèle appelé température.

## Comment notre start-up peut-elle exploiter les grands modèles de langage ?

Maintenant que nous avons une meilleure compréhension du fonctionnement interne d'un grand modèle de langage, examinons quelques exemples pratiques des tâches les plus courantes qu'ils peuvent effectuer assez bien, en gardant un œil sur notre scénario commercial.
Nous avons dit que la principale capacité d'un grand modèle de langage est de *générer un texte à partir de zéro, à partir d'une entrée textuelle écrite dans une langue naturelle*.

Mais quel genre d'entrée et de sortie textuelles ?
L'entrée d'un grand modèle de langage est connue sous le nom de prompt, tandis que la sortie est connue sous le nom de completion, terme qui fait référence au mécanisme du modèle de générer le prochain token pour compléter l'entrée actuelle. Nous allons approfondir ce qu'est un prompt et comment le concevoir de manière à en tirer le meilleur parti de notre modèle. Mais pour l'instant, disons simplement qu'un prompt peut inclure :

* Une **instruction** spécifiant le type de sortie que nous attendons du modèle. Cette instruction peut parfois inclure des exemples ou des données supplémentaires.

    1. Résumé d'un article, d'un livre, d'avis sur des produits et plus encore, ainsi qu'extraction d'informations à partir de données non structurées.
    
    ![Exemple de résumé](./images/summarization-example.png?WT.mc_id=academic-105485-koreyst)

    <br>
    
    2. Idéation créative et conception d'un article, d'un essai, d'une mission ou plus encore.
    
    ![Exemple d'écriture créative](./images/creative-writing-example.png?WT.mc_id=academic-105485-koreyst)

    <br>
    
* Une **question**, posée sous la forme d'une conversation avec un agent.
  
![Exemple de conversation](./images/conversation-example.png?WT.mc_id=academic-105485-koreyst)

<br>

* Un morceau de **texte à compléter**, qui est implicitement une demande d'aide à l'écriture.
   
![Exemple de complétion de texte](./images/text-completion-example.png?WT.mc_id=academic-105485-koreyst)

<br>

* Un morceau de **code** avec la demande d'explication et de documentation, ou un commentaire demandant de générer un morceau de code effectuant une tâche spécifique.

![Exemple de codage](./images/coding-example.png?WT.mc_id=academic-105485-koreyst)

<br>

Les exemples ci-dessus sont assez simples et ne veulent pas être une démonstration exhaustive des capacités des grands modèles de langage. Ils veulent simplement montrer le potentiel de l'utilisation de l'IA générative, en particulier mais pas exclusivement dans le contexte éducatif.

De plus, la sortie d'un modèle d'IA générative n'est pas parfaite et parfois la créativité du modèle peut jouer contre lui, résultant en une sortie qui est une combinaison de mots que l'utilisateur humain peut interpréter comme une mystification de la réalité, ou cela peut être offensant. L'IA générative n'est pas intelligente - du moins dans la définition la plus complète de l'intelligence, incluant le raisonnement critique et créatif ou l'intelligence émotionnelle ; elle n'est pas déterministe, et elle n'est pas fiable, car des fabrications, telles que des références, des contenus et des déclarations erronées, peuvent être combinées avec des informations correctes et présentées de manière persuasive et confiante. Dans les leçons suivantes, nous aborderons toutes ces limitations et nous verrons ce que nous pouvons faire pour les atténuer.

## Devoir

Votre devoir est de vous renseigner davantage sur l'[IA générative](https://en.wikipedia.org/wiki/Generative_artificial_intelligence?WT.mc_id=academic-105485-koreyst) et d'essayer d'identifier une zone où vous ajouteriez de l'IA générative aujourd'hui qui n'en a pas. Comment l'impact serait-il différent de le faire à l'ancienne, pouvez-vous faire quelque chose que vous ne pouviez pas faire avant, ou êtes-vous plus rapide ? Rédigez un résumé de 300 mots de ce que serait votre start-up AI de rêve et incluez des en-têtes tels que "Problème", "Comment j'utiliserais l'IA", "Impact" et éventuellement un plan d'affaires.

Si vous avez effectué cette tâche, vous pourriez même être prêt à postuler à l'incubateur de Microsoft, [Microsoft pour Startups Founders Hub](https://www.microsoft.com/startups?WT.mc_id=academic-105485-koreyst), nous offrons des crédits pour Azure, OpenAI, du mentorat et bien plus encore, consultez-le !

## Vérification des connaissances

Qu'est-ce qui est vrai à propos des grands modèles de langage ?

1. Vous obtenez exactement la même réponse à chaque fois.
1. Il fait les choses parfaitement, excellent pour ajouter des nombres, produire du code fonctionnel, etc.
1. La réponse peut varier malgré l'utilisation du même prompt. Il est également excellent pour vous donner un premier jet de quelque chose, que ce soit du texte ou du code. Mais vous devez améliorer les résultats.

R : 3, un LLM est non déterministe, la réponse varie, cependant, vous pouvez contrôler sa variance via un réglage de température. Vous ne devriez pas non plus vous attendre à ce qu'il fasse les choses parfaitement, il est là pour faire le travail difficile pour vous, ce qui signifie souvent que vous obtenez une bonne première tentative de quelque chose que vous devez améliorer progressivement.

## Excellent travail ! Poursuivez le voyage

Après avoir terminé cette leçon, consultez notre [collection d'apprentissage sur l'IA générative](https://aka.ms/genai-collection?WT.mc_id=academic-105485-koreyst) pour continuer à améliorer vos connaissances en matière d'


Avertissement: La traduction a été traduite à partir de son original par un modèle d'IA et peut ne pas être parfaite. Veuillez examiner la sortie et apporter les corrections nécessaires.