# Commencer avec ce cours

Nous sommes très heureux que vous commenciez ce cours et nous avons hâte de voir ce que vous serez inspiré de construire avec l'IA générative !

Pour assurer votre réussite, cette page décrit les étapes de configuration, les exigences techniques et où obtenir de l'aide si nécessaire.

## Étapes de configuration

Pour commencer ce cours, vous devrez suivre les étapes suivantes.

### 1. Forker ce repo

[Forker tout le repo](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) sur votre propre compte GitHub pour pouvoir modifier le code et relever les défis. Vous pouvez également [marquer (🌟) ce repo](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) pour le trouver plus facilement et trouver des repo connexes.

### 2. Créer un espace de code

Pour éviter tout problème de dépendance lors de l'exécution du code, nous recommandons d'exécuter ce cours dans un [Codespaces GitHub](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Cela peut être créé en sélectionnant l'option `Code` sur votre version forkée de ce repo et en sélectionnant l'option **Codespaces**.

![Dialog showing buttons to create a codespace](../../../translated_images/who-will-pay.6f2c33aa4143ba8edca4900340ceb6eb63fe85b96af52eafc2f6f52be3d3c6dd.fr.webp)

### 3. Stocker vos clés API

Il est important de garder vos clés API en sécurité lors de la construction de tout type d'application. Nous vous recommandons de ne pas stocker directement les clés API dans votre code. La mise en commit de ces détails dans un dépôt public pourrait entraîner des problèmes de sécurité et même des coûts indésirables s'ils sont utilisés par un acteur malveillant.

## Comment exécuter localement sur votre ordinateur

Pour exécuter le code localement sur votre ordinateur, vous devez avoir une version de [Python installée](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

Pour utiliser ensuite le repo, vous devez le cloner :

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

Une fois que vous avez tout vérifié, vous pouvez commencer !

### Installation de Miniconda (étape facultative)
[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) est un installateur léger pour l'installation de [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, ainsi que quelques packages.
Conda lui-même est un gestionnaire de packages, qui facilite la configuration et le basculement entre différents [**environnements virtuels**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) Python et packages. Il est également utile pour l'installation de packages qui ne sont pas disponibles via `pip`.

Vous pouvez suivre le [guide d'installation de MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) pour le configurer.

Avec Miniconda installé, vous devez cloner le [repo](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (si ce n'est pas déjà fait)

Ensuite, vous devez créer un environnement virtuel. Pour ce faire avec Conda, créez un nouveau fichier d'environnement (_environment.yml_). Si vous suivez le cours en utilisant Codespaces, créez-le dans le répertoire `.devcontainer`, donc `.devcontainer/environment.yml`.

Remplissez votre fichier d'environnement avec le code ci-dessous :
```yml
name: <environment-name>
channels:
 - defaults
dependencies:
- python=<python-version>
- openai
- python-dotenv
```

Le fichier d'environnement spécifie les dépendances dont nous avons besoin. `<environment-name>` fait référence au nom que vous souhaitez utiliser pour votre environnement Conda, et `<python-version>` est la version de Python que vous souhaitez utiliser, par exemple, `3` est la dernière version majeure de Python.

Une fois cela fait, vous pouvez créer votre environnement Conda en exécutant les commandes ci-dessous dans votre ligne de commande/terminal


```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Référez-vous au [guide des environnements Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) si vous rencontrez des problèmes.

### Utilisation de Visual Studio Code avec l'extension de prise en charge Python

Nous recommandons d'utiliser l'éditeur [Visual Studio Code (VS Code)](http://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) avec l'extension de prise en charge [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) installée pour ce cours. Cependant, il s'agit plus d'une recommandation que d'une exigence définitive.

> **Note**: En ouvrant le repo de cours dans VS Code, vous avez la possibilité de configurer le projet dans un conteneur. Cela est dû au [répertoire spécial `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) trouvé dans le repo de cours. Plus sur cela plus tard.

> **Note**: Une fois que vous avez cloné et ouvert le répertoire dans VS Code, il vous suggérera automatiquement d'installer une extension de prise en charge Python.

> **Note**: Si VS Code vous suggère de rouvrir le dépôt dans un conteneur, déclinez cette demande pour utiliser la version de Python installée localement.

### Utilisation de Jupyter dans le navigateur

Vous pouvez également travailler sur le projet en utilisant l'environnement [Jupyter](https://jupyter.org?WT.mc_id=academic-105485-koreyst) directement dans votre navigateur. Les environnements Jupyter classiques et [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) fournissent un environnement de développement plutôt agréable avec des fonctionnalités telles que l'autocomplétion, la mise en évidence de code, etc.

Pour démarrer Jupyter localement, accédez au terminal/ligne de commande, naviguez jusqu'au répertoire du cours et exécutez :

```bash
jupyter notebook
```

ou

```bash
jupyterhub
```

Cela démarrera une instance de Jupyter et l'URL pour y accéder sera affichée dans la fenêtre de la ligne de commande.

Une fois que vous accédez à l'URL, vous devriez voir le plan de cours et être en mesure de naviguer vers n'importe quel fichier `*.ipynb`. Par exemple, `08-building-search-applications/python/oai-solution.ipynb`.

### Exécution dans un conteneur

Une alternative à la configuration de tout sur votre ordinateur ou Codespace est d'utiliser un [conteneur](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). Le dossier spécial `.devcontainer` dans le repo de cours permet à VS Code de configurer le projet dans un conteneur. En dehors de Codespaces, cela nécessitera l'installation de Docker, et franchement, cela implique un peu de travail, donc nous le recommandons uniquement à ceux qui ont de l'expérience dans le travail avec des conteneurs.

L'une des meilleures façons de garder vos clés API sécurisées lors de l'utilisation de GitHub Codespaces est d'utiliser des secrets Codespace. Veuillez suivre le [guide de gestion des secrets Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) pour en savoir plus à ce sujet.

## Leçons et exigences techniques

Le cours comprend 6 leçons de concepts et 6 leçons de codage.

Pour les leçons de codage, nous utilisons le service Azure OpenAI. Vous aurez besoin d'accéder au service Azure OpenAI et d'une clé API pour exécuter ce code. Vous pouvez demander l'accès en [complétant cette application](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

En attendant que votre demande soit traitée, chaque leçon de codage comprend également un fichier `README.md` où vous pouvez afficher le code et les sorties.

## Utilisation du service Azure OpenAI pour la première fois

Si c'est votre première fois de travailler avec le service Azure OpenAI, veuillez suivre ce guide sur la façon de [créer et déployer une ressource de service Azure OpenAI.](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## Utilisation de l'API OpenAI pour la première fois

Si c'est votre première fois de travailler avec l'API OpenAI, veuillez suivre le guide sur la façon de [créer et utiliser l'interface.](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## Rencontrez d'autres apprenants

Nous avons créé des canaux dans notre serveur Discord [AI Community Discord server](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) officiel pour rencontrer d'autres apprenants. C'est un excellent moyen de réseauter avec d'autres entrepreneurs, constructeurs, étudiants et toute personne cherchant à monter en compétences en IA générative.

[![Join discord channel](https://dcbadge.vercel.app/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

L'équipe du projet sera également sur ce serveur Discord pour aider tous les apprenants.

## Contribuer

Ce cours est une initiative open source. Si vous voyez des domaines d'amélioration ou des problèmes, veuillez créer une [demande de tirage](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) ou enregistrer une [issue GitHub](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

L'équipe du projet suivra toutes les contributions. Contribuer à l'open source est un moyen incroyable de construire votre carrière en IA générative.

La plupart des contributions nécessitent que vous acceptiez un accord de licence de contributeur (CLA) déclarant que vous avez le droit et que vous accordez effectivement les droits d'utiliser votre contribution. Pour plus de détails, visitez [CLA, le site Web de l'accord de licence de contributeur](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Important : lors de la traduction du texte de ce repo, veuillez vous assurer de ne pas utiliser la traduction automatique. Nous vérifierons les traductions via la communauté, donc veuillez vous porter volontaire pour les traductions dans les langues où vous êtes compétent.

Lorsque vous soumettez une demande de tirage, un bot CLA déterminera automatiquement si vous devez fournir un CLA et décorera le PR de manière appropriée (par exemple, étiquette, commentaire). Suivez simplement les instructions fournies par le bot. Vous n'aurez à le faire qu'une seule fois pour tous les dépôts utilisant notre CLA.

Ce projet a adopté le [Code de conduite open source de Microsoft](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). Pour plus d'informations, lisez la FAQ sur le Code de conduite ou contactez [Email opencode](opencode@microsoft.com) pour toute question ou commentaire supplémentaire.

## Commençons

Maintenant que vous avez terminé les étapes nécessaires pour terminer ce cours, commençons par une [introduction à l'IA générative et aux LLMs](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).


Avertissement : La traduction a été traduite à partir de son original par un modèle d'IA et peut ne pas être parfaite. Veuillez examiner la sortie et apporter toutes les corrections nécessaires.