# Commencer avec ce cours

Nous sommes très enthousiastes à l'idée de vous voir commencer ce cours et de voir ce qui vous inspire à construire avec l'IA générative !

Pour assurer votre succès, cette page décrit les étapes de configuration, les exigences techniques et où obtenir de l'aide en cas de besoin.

## Étapes de configuration

Pour commencer ce cours, vous devrez suivre les étapes suivantes.

### 1. Forker ce Repo

[Forker l'intégralité de ce repo](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) sur votre propre compte GitHub pour pouvoir modifier le code et relever les défis. Vous pouvez également [marquer (🌟) ce repo](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) pour le trouver et trouver des repos connexes plus facilement.

### 2. Créer un codespace

Pour éviter tout problème de dépendance lors de l'exécution du code, nous recommandons d'exécuter ce cours dans un [Codespaces GitHub](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Cela peut être créé en sélectionnant l'option `Code` sur votre version forkée de ce repo et en sélectionnant l'option **Codespaces**.

![Dialogue montrant des boutons pour créer un codespace](./images/who-will-pay.webp?WT.mc_id=academic-105485-koreyst)

### 3. Stocker vos clés d'API

Il est important de garder vos clés d'API en sécurité lors de la construction de tout type d'application. Nous vous recommandons de ne pas stocker directement les clés d'API dans votre code. La mise en commit de ces détails dans un dépôt public pourrait entraîner des problèmes de sécurité et même des coûts indésirables s'ils sont utilisés par un acteur malveillant.

## Comment exécuter localement sur votre ordinateur

Pour exécuter le code localement sur votre ordinateur, vous devrez avoir une version de [Python installée](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

Ensuite, pour utiliser le dépôt, vous devez le cloner :

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

Une fois que tout est vérifié, vous pouvez commencer !

### Installation de Miniconda (étape facultative)
[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) est un installateur léger pour installer [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, ainsi que quelques packages.
Conda lui-même est un gestionnaire de packages, qui facilite la configuration et le basculement entre différents environnements virtuels Python [**virtual environments**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) et packages. Il est également pratique pour installer des packages qui ne sont pas disponibles via `pip`.

Vous pouvez suivre le [guide d'installation de MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) pour le configurer.

Avec Miniconda installé, vous devez cloner le [dépôt](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (si vous ne l'avez pas déjà fait)

Ensuite, vous devez créer un environnement virtuel. Pour ce faire avec Conda, créez un nouveau fichier d'environnement (_environment.yml_). Si vous suivez cette procédure avec Codespaces, créez-le dans le répertoire `.devcontainer`, donc `.devcontainer/environment.yml`.

Allez-y et remplissez votre fichier d'environnement avec le code ci-dessous :
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

Avec cela fait, vous pouvez continuer et créer votre environnement Conda en exécutant les commandes ci-dessous dans votre ligne de commande/terminal


```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Reportez-vous au [guide des environnements Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) si vous rencontrez des problèmes.

### Utilisation de Visual Studio Code avec l'extension de prise en charge Python

Nous recommandons d'utiliser l'éditeur [Visual Studio Code (VS Code)](http://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) avec l'extension de prise en charge [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) installée pour ce cours. Cependant, il s'agit davantage d'une recommandation que d'une exigence définitive.

> **Remarque** : En ouvrant le dépôt de cours dans VS Code, vous avez la possibilité de configurer le projet dans un conteneur. Cela est dû au [répertoire spécial `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) trouvé dans le dépôt de cours. Plus à ce sujet plus tard.

> **Remarque** : Une fois que vous avez cloné et ouvert le répertoire dans VS Code, il vous suggérera automatiquement d'installer une extension de prise en charge Python.

> **Remarque** : Si VS Code vous suggère de rouvrir le dépôt dans un conteneur, déclinez cette demande pour utiliser la version de Python installée localement.

### Utilisation de Jupyter dans le navigateur

Vous pouvez également travailler sur le projet en utilisant l'environnement [Jupyter](https://jupyter.org?WT.mc_id=academic-105485-koreyst) directement dans votre navigateur. Les environnements Jupyter classiques et [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) fournissent un environnement de développement assez agréable avec des fonctionnalités telles que l'autocomplétion, la mise en évidence du code, etc.

Pour démarrer Jupyter localement, rendez-vous dans le terminal/ligne de commande, naviguez jusqu'au répertoire du cours et exécutez :

```bash
jupyter notebook
```

ou

```bash
jupyterhub
```

Cela démarrera une instance de Jupyter et l'URL pour y accéder sera affichée dans la fenêtre de la ligne de commande.

Une fois que vous accédez à l'URL, vous devriez voir le plan du cours et pouvoir accéder à tout fichier `*.ipynb`. Par exemple, `08-building-search-applications/python/oai-solution.ipynb`.

### Exécution dans un conteneur

Une alternative à la configuration de tout sur votre ordinateur ou Codespace consiste à utiliser un [conteneur](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). Le dossier spécial `.devcontainer` dans le dépôt de cours permet à VS Code de configurer le projet dans un conteneur. En dehors de Codespaces, cela nécessitera l'installation de Docker, et franchement, cela implique un peu de travail, nous recommandons donc cela uniquement à ceux qui ont de l'expérience dans le travail avec les conteneurs.

L'une des meilleures façons de sécuriser vos clés d'API lors de l'utilisation de GitHub Codespaces est d'utiliser les secrets Codespace. Veuillez suivre le [guide de gestion des secrets Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) pour en savoir plus à ce sujet.

## Leçons et exigences techniques

Le cours comporte 6 leçons de concepts et 6 leçons de codage.

Pour les leçons de codage, nous utilisons le service Azure OpenAI. Vous aurez besoin d'un accès au service Azure OpenAI et d'une clé d'API pour exécuter ce code. Vous pouvez demander un accès en [remplissant cette demande](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

En attendant que votre demande soit traitée, chaque leçon de codage comprend également un fichier `README.md` où vous pouvez voir le code et les sorties.

## Utilisation du service Azure OpenAI pour la première fois

Si c'est la première fois que vous travaillez avec le service Azure OpenAI, suivez ce guide sur la façon de [créer et déployer une ressource Azure OpenAI Service](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst).

## Utilisation de l'API OpenAI pour la première fois

Si c'est la première fois que vous travaillez avec l'API OpenAI, suivez le guide sur la façon de [créer et utiliser l'interface.](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## Rencontrer d'autres apprenants

Nous avons créé des canaux sur notre serveur Discord [AI Community Discord server](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) officiel pour rencontrer d'autres apprenants. C'est un excellent moyen de réseauter avec d'autres entrepreneurs, constructeurs, étudiants et toute personne cherchant à progresser dans l'IA générative.

[![Join discord channel](https://dcbadge.vercel.app/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

L'équipe du projet sera également sur ce serveur Discord pour aider tous les apprenants.

## Contribuer

Ce cours est une initiative open source. Si vous voyez des zones d'amélioration ou des problèmes, veuillez créer une [demande de pull](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) ou enregistrer un [problème GitHub](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

L'équipe du projet suivra toutes les contributions. Contribuer à l'open source est un moyen incroyable de construire votre carrière en IA générative.

La plupart des contributions nécessitent que vous acceptiez un Accord de licence de contributeur (CLA) déclarant que vous avez le droit et que vous accordez effectivement les droits d'utiliser votre contribution. Pour plus de détails, consultez [CLA, le site Web de l'Accord de licence de contributeur](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Important : lors de la traduction de textes dans ce repo, veuillez vous assurer de ne pas utiliser la traduction automatique. Nous vérifierons les traductions via la communauté, veuillez donc vous porter volontaire pour les traductions dans les langues que vous maîtrisez.

Lorsque vous soumettez une demande de pull, un robot CLA déterminera automatiquement si vous devez fournir un CLA et décorera le PR de manière appropriée (par exemple, étiquette, commentaire). Suivez simplement les instructions fournies par le robot. Vous n'aurez à le faire qu'une seule fois pour tous les dépôts utilisant notre CLA.

Ce projet a adopté le [Code de conduite open source de Microsoft](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). Pour plus d'informations, lisez la FAQ du Code de conduite ou contactez [Email opencode](opencode@microsoft.com) pour toute question ou commentaire supplémentaire.

## Commençons

Maintenant que vous avez terminé les étapes nécessaires pour terminer ce cours, commençons par [une introduction à l'IA générative et aux LLM](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).


Avertissement : La traduction a été effectuée à partir d'un modèle d'IA et peut ne pas être parfaite. Veuillez vérifier la sortie et apporter les corrections nécessaires.