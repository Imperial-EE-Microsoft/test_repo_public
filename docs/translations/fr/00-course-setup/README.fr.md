# Commencer avec ce cours

Nous sommes très enthousiastes à l'idée que vous commenciez ce cours et de voir ce que vous serez inspiré de construire avec l'IA générative !

Pour assurer votre succès, cette page décrit les étapes de configuration, les exigences techniques et où obtenir de l'aide si nécessaire.

## Étapes de configuration

Pour commencer ce cours, vous devrez suivre les étapes suivantes.

### 1. Forker ce repo

[Forker l'intégralité de ce repo](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) sur votre propre compte GitHub pour pouvoir modifier tout code et compléter les défis. Vous pouvez également [mettre en favori (🌟) ce repo](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) pour le trouver et trouver des repos connexes plus facilement.

### 2. Créer un codespace

Pour éviter tout problème de dépendance lors de l'exécution du code, nous recommandons d'exécuter ce cours dans un [Codespaces GitHub](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Cela peut être créé en sélectionnant l'option `Code` sur votre version forkée de ce repo et en sélectionnant l'option **Codespaces**.

![Dialogue montrant des boutons pour créer un codespace](./images/who-will-pay.webp?WT.mc_id=academic-105485-koreyst)

### 3. Stocker vos clés API

Il est important de garder vos clés API en sécurité lorsque vous construisez tout type d'application. Nous recommandons de ne pas stocker directement les clés API dans votre code. La mise en commit de ces détails dans un dépôt public pourrait entraîner des problèmes de sécurité et même des coûts indésirables s'ils sont utilisés par un acteur malveillant.

## Comment exécuter localement sur votre ordinateur

Pour exécuter le code localement sur votre ordinateur, vous devez avoir une version de [Python installée](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

Ensuite, pour utiliser le dépôt, vous devez le cloner :

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

Une fois que vous avez tout vérifié, vous pouvez commencer !

### Installation de Miniconda (étape facultative)
[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) est un installateur léger pour installer [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, ainsi que quelques packages.
Conda lui-même est un gestionnaire de packages, qui facilite la configuration et le passage entre différents [**environnements virtuels**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) Python et packages. Il est également pratique pour installer des packages qui ne sont pas disponibles via `pip`.

Vous pouvez suivre le [guide d'installation de MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) pour le configurer.

Avec Miniconda installé, vous devez cloner le [dépôt](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (si vous ne l'avez pas déjà fait)

Ensuite, vous devez créer un environnement virtuel. Pour ce faire avec Conda, créez un nouveau fichier d'environnement (_environment.yml_). Si vous suivez le cours en utilisant Codespaces, créez-le dans le répertoire `.devcontainer`, donc `.devcontainer/environment.yml`.

Remplissez votre fichier d'environnement avec l'extrait ci-dessous :

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
conda env create --name ai4beg --file .devcontainer/environment.yml # Le sous-chemin .devcontainer s'applique uniquement aux configurations de Codespaces
conda activate ai4beg
```

Référez-vous au [guide des environnements Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) si vous rencontrez des problèmes.

### Utilisation de Visual Studio Code avec l'extension de prise en charge de Python

Nous recommandons d'utiliser l'éditeur [Visual Studio Code (VS Code)](http://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) avec l'extension [Python support extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) installée pour ce cours. Cependant, il s'agit davantage d'une recommandation que d'une exigence définitive.

> **Remarque** : En ouvrant le dépôt de cours dans VS Code, vous avez la possibilité de configurer le projet dans un conteneur. Cela est dû au [répertoire spécial `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) trouvé dans le dépôt de cours. Plus d'informations à ce sujet plus tard.

> **Remarque** : Une fois que vous avez cloné et ouvert le répertoire dans VS Code, il vous suggérera automatiquement d'installer une extension de prise en charge de Python.

> **Remarque** : Si VS Code vous suggère de rouvrir le dépôt dans un conteneur, déclinez cette demande afin d'utiliser la version de Python installée localement.

### Utilisation de Jupyter dans le navigateur

Vous pouvez également travailler sur le projet en utilisant l'environnement [Jupyter](https://jupyter.org?WT.mc_id=academic-105485-koreyst) directement dans votre navigateur. Les deux Jupyter classique et [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) offrent un environnement de développement assez agréable avec des fonctionnalités telles que l'auto-complétion, la mise en évidence du code, etc.

Pour démarrer Jupyter localement, rendez-vous dans le terminal/l'invite de commande, accédez au répertoire du cours et exécutez :

```bash
jupyter notebook
```

ou

```bash
jupyterhub
```

Cela démarrera une instance de Jupyter et l'URL pour y accéder sera affichée dans la fenêtre de la ligne de commande.

Une fois que vous avez accédé à l'URL, vous devriez voir le plan de cours et être en mesure de naviguer vers n'importe quel fichier `*.ipynb`. Par exemple, `08-building-search-applications/python/oai-solution.ipynb`.

### Exécution dans un conteneur

Une alternative à la configuration de tout sur votre ordinateur ou sur Codespace est d'utiliser un [conteneur](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). Le dossier spécial `.devcontainer` dans le dépôt de cours permet à VS Code de configurer le projet dans un conteneur. En dehors de Codespaces, cela nécessitera l'installation de Docker, et franchement, cela implique un peu de travail, nous le recommandons donc uniquement à ceux qui ont de l'expérience dans le travail avec des conteneurs.

L'une des meilleures façons de sécuriser vos clés API lors de l'utilisation de GitHub Codespaces est d'utiliser des secrets Codespace. Veuillez suivre le [guide de gestion des secrets Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) pour en savoir plus à ce sujet.

## Leçons et exigences techniques

Le cours comprend 6 leçons de concepts et 6 leçons de codage.

Pour les leçons de codage, nous utilisons le service Azure OpenAI. Vous aurez besoin d'accéder au service Azure OpenAI et d'une clé API pour exécuter ce code. Vous pouvez demander l'accès en [remplissant cette demande](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

Pendant que vous attendez que votre demande soit traitée, chaque leçon de codage comprend également un fichier `README.md` où vous pouvez voir le code et les sorties.

## Utilisation du service Azure OpenAI pour la première fois

Si c'est la première fois que vous travaillez avec le service Azure OpenAI, suivez ce guide sur la façon de [créer et déployer une ressource de service Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst).

## Utilisation de l'API OpenAI pour la première fois

Si c'est la première fois que vous travaillez avec l'API OpenAI, suivez le guide sur la façon de [créer et utiliser l'interface](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst).

## Rencontrez d'autres apprenants

Nous avons créé des canaux dans notre serveur officiel [AI Community Discord](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) pour rencontrer d'autres apprenants. C'est un excellent moyen de réseauter avec d'autres entrepreneurs, constructeurs, étudiants et toute personne cherchant à se perfectionner dans l'IA générative.

[![Rejoignez le canal Discord](https://dcbadge.vercel.app/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

L'équipe du projet sera également sur ce serveur Discord pour aider les apprenants.

## Contribuer

Ce cours est une initiative open source. Si vous voyez des zones d'amélioration ou des problèmes, veuillez créer une [demande de pull](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) ou signaler un [problème GitHub](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

L'équipe du projet suivra toutes les contributions. Contribuer à l'open source est un moyen incroyable de construire votre carrière en IA générative.

La plupart des contributions nécessitent que vous acceptiez un accord de licence de contributeur (CLA) déclarant que vous avez le droit et que vous accordez effectivement les droits d'utiliser votre contribution. Pour plus de détails, consultez le site [CLA, Contributor License Agreement](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Important : lors de la traduction de texte dans ce dépôt, veuillez vous assurer de ne pas utiliser de traduction automatique. Nous vérifierons les traductions via la communauté, donc veuillez vous porter volontaire uniquement pour les traductions dans les langues que vous maîtrisez.

Lorsque vous soumettez une demande de pull, un bot CLA déterminera automatiquement si vous devez fournir un CLA et décorera le PR de manière appropriée (par exemple, étiquette, commentaire). Suivez simplement les instructions fournies par le bot. Vous n'aurez à le faire qu'une fois pour tous les dépôts utilisant notre CLA.

Ce projet a adopté le [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). Pour plus d'informations, consultez la FAQ du Code de conduite ou contactez [Email opencode](opencode@microsoft.com) pour toute question ou commentaire supplémentaire.

## Commençons

Maintenant que vous avez terminé les étapes nécessaires pour terminer ce cours, commençons par une [introduction à l'IA générative et aux LLM](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).


Avertissement : La traduction a été traduite à partir de son original par un modèle d'IA et peut ne pas être parfaite. Veuillez vérifier la sortie et apporter les corrections nécessaires.