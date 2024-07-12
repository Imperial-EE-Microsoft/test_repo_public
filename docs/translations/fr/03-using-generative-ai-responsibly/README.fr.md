# Utiliser l'IA générative de manière responsable

[![Utiliser l'IA générative de manière responsable](./images/03-lesson-banner.png?WT.mc_id=academic-105485-koreyst)]()

> **Vidéo à venir**

Il est facile d'être fasciné par l'IA et l'IA générative en particulier, mais vous devez considérer comment vous l'utiliseriez de manière responsable. Vous devez considérer des choses comme la manière de garantir que la sortie est juste, non nuisible et plus encore. Ce chapitre vise à vous fournir le contexte mentionné, ce qu'il faut considérer et comment prendre des mesures actives pour améliorer votre utilisation de l'IA.

## Introduction

Cette leçon abordera :

- Pourquoi vous devriez donner la priorité à l'IA responsable lors de la création d'applications d'IA générative.
- Les principes fondamentaux de l'IA responsable et comment ils se rapportent à l'IA générative.
- Comment mettre en pratique ces principes d'IA responsable grâce à une stratégie et des outils.

## Objectifs d'apprentissage

Après avoir terminé cette leçon, vous saurez :

- L'importance de l'IA responsable lors de la création d'applications d'IA générative.
- Quand penser et appliquer les principes fondamentaux de l'IA responsable lors de la création d'applications d'IA générative.
- Quels outils et stratégies sont disponibles pour vous permettre de mettre en pratique le concept d'IA responsable.

## Principes de l'IA responsable

L'excitation autour de l'IA générative n'a jamais été aussi forte. Cette excitation a attiré de nombreux nouveaux développeurs, l'attention et des financements dans cet espace. Bien que cela soit très positif pour toute personne cherchant à construire des produits et des entreprises utilisant l'IA générative, il est également important que nous procédions de manière responsable.

Tout au long de ce cours, nous nous concentrons sur la construction de notre startup et de notre produit d'éducation en IA. Nous utiliserons les principes de l'IA responsable : l'équité, l'inclusion, la fiabilité/sécurité, la sécurité et la confidentialité, la transparence et la responsabilité. Avec ces principes, nous explorerons comment ils se rapportent à notre utilisation de l'IA générative dans nos produits.

## Pourquoi devriez-vous donner la priorité à l'IA responsable

Lors de la construction d'un produit, adopter une approche centrée sur l'humain en gardant à l'esprit les intérêts de l'utilisateur conduit aux meilleurs résultats.

L'unicité de l'IA générative réside dans sa capacité à créer des réponses utiles, des informations, des orientations et du contenu pour les utilisateurs. Cela peut être fait sans beaucoup d'étapes manuelles, ce qui peut conduire à des résultats très impressionnants. Sans une planification et des stratégies adéquates, cela peut malheureusement également conduire à des résultats nuisibles pour vos utilisateurs, votre produit et la société dans son ensemble.

Regardons quelques-uns (mais pas tous) de ces résultats potentiellement nuisibles :

### Hallucinations

Les hallucinations sont un terme utilisé pour décrire lorsque LLM produit du contenu qui est soit complètement absurde, soit quelque chose que nous savons être factuellement incorrect en nous basant sur d'autres sources d'information.

Prenons par exemple que nous construisons une fonctionnalité pour notre startup qui permet aux étudiants de poser des questions historiques à un modèle. Un étudiant pose la question « Qui a été le seul survivant du Titanic ? »

Le modèle produit une réponse comme celle ci-dessous :

![Prompt disant "Qui a été le seul survivant du Titanic"](../03-using-generative-ai-responsibly/images/ChatGPT-titanic-survivor-prompt.webp?WT.mc_id=academic-105485-koreyst)

> *(Source : [Flying bisons](https://flyingbisons.com?WT.mc_id=academic-105485-koreyst))*

C'est une réponse très confiante et complète. Malheureusement, elle est incorrecte. Même avec un minimum de recherche, on découvrirait qu'il y avait plus d'un survivant de la catastrophe du Titanic. Pour un étudiant qui commence tout juste à rechercher ce sujet, cette réponse peut être suffisamment persuasive pour ne pas être remise en question et traitée comme un fait. Les conséquences de cela peuvent conduire à ce que le système d'IA soit peu fiable et ait un impact négatif sur la réputation de notre startup.

À chaque itération de n'importe quel LLM donné, nous avons constaté des améliorations de performance pour minimiser les hallucinations. Même avec cette amélioration, nous, en tant que constructeurs et utilisateurs d'applications, devons toujours rester conscients de ces limites.

### Contenu nuisible

Nous avons vu dans la section précédente quand un LLM produit des réponses incorrectes ou absurdes. Un autre risque dont nous devons être conscients est lorsque le modèle répond avec du contenu nuisible.

Le contenu nuisible peut être défini comme :

- Fournir des instructions ou encourager l'automutilation ou des dommages à certains groupes.
- Contenu haineux ou dénigrant.
- Guider la planification de tout type d'attaque ou d'actes violents.
- Fournir des instructions sur la façon de trouver du contenu illégal ou de commettre des actes illégaux.
- Afficher du contenu sexuellement explicite.

Pour notre startup, nous voulons nous assurer que nous avons les bons outils et stratégies en place pour empêcher ce type de contenu d'être vu par les étudiants.

### Manque d'équité

L'équité est définie comme « s'assurer qu'un système d'IA est exempt de biais et de discrimination et qu'il traite tout le monde de manière juste et égale ». Dans le monde de l'IA générative, nous voulons nous assurer que les visions du monde exclusives des groupes marginalisés ne sont pas renforcées par la sortie du modèle.

Ces types de sorties ne sont pas seulement destructeurs pour la construction d'expériences de produits positives pour nos utilisateurs, mais ils causent également des préjudices supplémentaires à la société. En tant que constructeurs d'applications, nous devrions toujours garder à l'esprit une base d'utilisateurs large et diversifiée lors de la construction de solutions avec l'IA générative.

## Comment utiliser l'IA générative de manière responsable

Maintenant que nous avons identifié l'importance de l'IA générative responsable, examinons 4 étapes que nous pouvons prendre pour construire nos solutions d'IA de manière responsable :

![Cycle d'atténuation](./images/mitigate-cycle.png?WT.mc_id=academic-105485-koreyst)

### Mesurer les dommages potentiels

En testant des ensembles de données diversifiés, nous pouvons mesurer les dommages potentiels causés par le modèle et ses réponses.

Puisque notre startup construit un produit d'éducation, il serait bon de préparer une liste de prompts liés à l'éducation. Cela pourrait couvrir un certain sujet, des faits historiques et des prompts sur la vie étudiante.

### Atténuer les dommages potentiels

Il est maintenant temps de trouver des moyens de prévenir ou de limiter les dommages potentiels causés par le modèle et ses réponses. Nous pouvons examiner cela en 4 couches différentes :

![Couches d'atténuation](./images/mitigation-layers.png?WT.mc_id=academic-105485-koreyst)

- **Modèle**. Choisir le bon modèle pour le bon cas d'utilisation. Les modèles plus grands et plus complexes comme GPT-4 peuvent causer plus de risques de contenu nuisible lorsqu'ils sont appliqués à des cas d'utilisation plus petits et plus spécifiques. L'utilisation de vos données d'entraînement pour un ajustement fin réduit également le risque de contenu nuisible.

- **Système de sécurité**. Un système de sécurité est un ensemble d'outils et de configurations sur la plateforme qui sert le modèle et qui aide à atténuer les dommages. Un exemple de ceci est le système de filtrage de contenu sur le service Azure OpenAI. Les systèmes doivent également détecter les attaques de jailbreak et les activités non désirées telles que les demandes de bots.

- **Métaprompts**. Les métaprompts et l'ancrage sont des moyens de diriger ou de limiter le modèle en fonction de certains comportements et informations. Cela pourrait être l'utilisation d'entrées système pour définir certaines limites du modèle. De plus, fournir des sorties qui sont plus pertinentes pour la portée ou le domaine du système.

 Il peut également s'agir d'utiliser des techniques comme la génération augmentée de récupération (RAG) pour que le modèle ne tire des informations que d'une sélection de sources fiables. Il y a une leçon plus tard dans ce cours pour [la construction d'applications de recherche](../08-building-search-applications/README.md?WT.mc_id=academic-105485-koreyst)

- **Expérience utilisateur**. La dernière couche est celle où l'utilisateur interagit directement avec le modèle via l'interface de notre application. De cette façon, nous pouvons concevoir l'interface utilisateur pour limiter l'utilisateur sur les types d'entrées qu'il peut envoyer au modèle ainsi que le texte ou les images affichées à l'utilisateur. Lors du déploiement de l'application d'IA, nous devons également être transparents sur ce que notre application d'IA générative peut et ne peut pas faire.

Nous avons une leçon entière consacrée à la [conception UX pour les applications d'IA](../12-designing-ux-for-ai-applications/README.md?WT.mc_id=academic-105485-koreyst)

- **Évaluer le modèle**. Travailler avec des LLM peut être difficile car nous n'avons pas toujours le contrôle sur les données sur lesquelles le modèle a été formé. Quoi qu'il en soit, nous devons toujours évaluer la performance et les sorties du modèle. Il est toujours important de mesurer l'exactitude, la similarité, l'ancrage et la pertinence de la sortie du modèle. Cela aide à fournir de la transparence et de la confiance aux parties prenantes et aux utilisateurs.

### Opérer une solution d'IA générative responsable

La construction d'une pratique opérationnelle autour de vos applications d'IA est la dernière étape. Cela comprend le partenariat avec d'autres parties de notre startup comme le service juridique et la sécurité pour nous assurer que nous sommes conformes à toutes les politiques réglementaires. Avant le lancement, nous voulons également élaborer des plans autour de la livraison, de la gestion des incidents et du retour en arrière pour éviter toute nuisance à nos utilisateurs en croissance.

## Outils

Bien que le travail de développement de solutions d'IA responsables puisse sembler beaucoup, c'est un travail qui vaut bien l'effort. À mesure que le domaine de l'IA générative se développe, des outils pour aider les développeurs à intégrer efficacement la responsabilité dans leurs flux de travail vont mûrir. Par exemple, [Azure AI Content Safety](https://learn.microsoft.com/azure/ai-services/content-safety/overview?WT.mc_id=academic-105485-koreyst) peut aider à détecter le contenu nuisible et les images via une demande API.

## Vérification des connaissances

Quelles sont les choses auxquelles vous devez faire attention pour assurer une utilisation responsable de l'IA ?

1. Que la réponse soit correcte.
1. L'utilisation nuisible, que l'IA ne soit pas utilisée à des fins criminelles.
1. S'assurer que l'IA est exempte de biais et de discrimination.

R : 2 et 3 sont correctes. L'IA responsable vous aide à considérer comment atténuer les effets nuisibles et les biais, et plus encore.

## 🚀 Défi

Lisez [Azure AI Content Safety](https://learn.microsoft.com/azure/ai-services/content-safety/overview?WT.mc_id=academic-105485-koreyst) et voyez ce que vous pouvez adopter pour votre utilisation.

## Excellent travail, continuez votre apprentissage

Après avoir terminé cette leçon, consultez notre [collection d'apprentissage sur l'IA générative](https://aka.ms/genai-collection?WT.mc_id=academic-105485-koreyst) pour continuer à améliorer vos connaissances en IA générative !

Passez à la leçon 4 où nous examinerons les [fondamentaux de l'ingénierie des prompts](../04-prompt-engineering-fundamentals/README.md?WT.mc_id=academic-105485-koreyst)!


Avertissement : La traduction a été traduite à partir de son original par un modèle d'IA et peut ne pas être parfaite. Veuillez vérifier la sortie et apporter les corrections nécessaires.