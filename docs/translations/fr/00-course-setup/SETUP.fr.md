# Configurer votre environnement de développement

Nous avons configuré ce référentiel et ce cours avec un [conteneur de développement](https://containers.dev?WT.mc_id=academic-105485-koreyst) qui possède un runtime universel qui peut prendre en charge le développement Python3, .NET, Node.js et Java. La configuration associée est définie dans le fichier `devcontainer.json` situé dans le dossier `.devcontainer/` à la racine de ce référentiel.

Pour activer le conteneur de développement, lancez-le dans [GitHub Codespaces](https://docs.github.com/en/codespaces/overview?WT.mc_id=academic-105485-koreyst) (pour un runtime hébergé dans le cloud) ou dans [Docker Desktop](https://docs.docker.com/desktop/?WT.mc_id=academic-105485-koreyst) (pour un runtime hébergé localement). Lisez [cette documentation](https://code.visualstudio.com/docs/devcontainers/containers?WT.mc_id=academic-105485-koreyst) pour plus de détails sur le fonctionnement des conteneurs de développement dans VS Code.

> [!TIP]  
> Nous vous recommandons d'utiliser GitHub Codespaces pour un démarrage rapide avec un effort minimal. Il fournit un quota d'utilisation gratuit et généreux pour les comptes personnels. Configurez les [délais d'expiration](https://docs.github.com/codespaces/setting-your-user-preferences/setting-your-timeout-period-for-github-codespaces?WT.mc_id=academic-105485-koreyst) pour arrêter ou supprimer les codespaces inactifs afin de maximiser votre utilisation de quota.

## 1. Exécuter les missions

Chaque leçon aura des missions _optionnelles_ qui peuvent être fournies dans un ou plusieurs langages de programmation, notamment: Python, .NET/C#, Java et JavaScript/TypeScript. Cette section fournit des orientations générales liées à l'exécution de ces missions.

### 1.1 Missions Python

Les missions Python sont fournies sous forme d'applications (fichiers `.py`) ou de carnets Jupyter (fichiers `.ipynb`).
- Pour exécuter le carnet, ouvrez-le dans Visual Studio Code, puis cliquez sur _Select Kernel_ (en haut à droite) et sélectionnez l'option Python 3 par défaut affichée. Vous pouvez maintenant exécuter tout avec _Run All_.
- Pour exécuter des applications Python à partir de la ligne de commande, suivez les instructions spécifiques à chaque mission pour vous assurer de sélectionner les bons fichiers et de fournir les arguments requis.

## 2. Configuration des fournisseurs

Les missions **peuvent** également être configurées pour fonctionner avec un ou plusieurs déploiements de modèle de langage de grande taille (LLM) via un fournisseur de service pris en charge tel que OpenAI, Azure ou Hugging Face. Ceux-ci fournissent un _point de terminaison hébergé_ (API) auquel nous pouvons accéder de manière programmatique avec les bonnes informations d'identification (clé API ou jeton). Dans ce cours, nous discutons de ces fournisseurs:

 - [OpenAI](https://platform.openai.com/docs/models?WT.mc_id=academic-105485-koreyst) avec des modèles divers, y compris la série principale GPT.
 - [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/?WT.mc_id=academic-105485-koreyst) pour les modèles OpenAI avec une disponibilité entreprise en focus.
 - [Hugging Face](https://huggingface.co/docs/hub/index?WT.mc_id=academic-105485-koreyst) pour les modèles open-source et le serveur d'inférence.

**Vous devrez utiliser vos propres comptes pour ces exercices**. Les missions sont optionnelles, vous pouvez donc choisir de configurer un, tous - ou aucun - des fournisseurs en fonction de vos intérêts. Voici quelques orientations pour vous inscrire :

| Inscription | Coût | Clé API | Terrain de jeu | Commentaires |
|:---|:---|:---|:---|:---|
| [OpenAI](https://platform.openai.com/signup?WT.mc_id=academic-105485-koreyst)| [Tarification](https://openai.com/pricing#language-models?WT.mc_id=academic-105485-koreyst)| [Basé sur le projet](https://platform.openai.com/api-keys?WT.mc_id=academic-105485-koreyst) | [Sans code, Web](https://platform.openai.com/playground?WT.mc_id=academic-105485-koreyst) | Plusieurs modèles disponibles |
| [Azure](https://aka.ms/azure/free?WT.mc_id=academic-105485-koreyst)| [Tarification](https://azure.microsoft.com/pricing/details/cognitive-services/openai-service/?WT.mc_id=academic-105485-koreyst)| [SDK Quickstart](https://learn.microsoft.com/azure/ai-services/openai/quickstart?WT.mc_id=academic-105485-koreyst)| [Studio Quickstart](https://learn.microsoft.com/azure/ai-services/openai/quickstart?WT.mc_id=academic-105485-koreyst) |  [Doit s'inscrire pour y accéder](https://learn.microsoft.com/azure/ai-services/openai/?WT.mc_id=academic-105485-koreyst)|
| [Hugging Face](https://huggingface.co/join?WT.mc_id=academic-105485-koreyst) | [Tarification](https://huggingface.co/pricing) | [Jetons d'accès](https://huggingface.co/docs/hub/security-tokens?WT.mc_id=academic-105485-koreyst) | [Hugging Chat](https://huggingface.co/chat/?WT.mc_id=academic-105485-koreyst)| [Hugging Chat a des modèles limités](https://huggingface.co/chat/models?WT.mc_id=academic-105485-koreyst) |
| | | | | |

Suivez les instructions ci-dessous pour _configurer_ ce référentiel pour une utilisation avec différents fournisseurs. Les missions qui nécessitent un fournisseur spécifique contiendront l'une de ces étiquettes dans leur nom de fichier :
 - `aoai` - nécessite un point de terminaison Azure OpenAI, une clé
 - `oai` - nécessite un point de terminaison OpenAI, une clé
 - `hf` - nécessite un jeton Hugging Face

Vous pouvez configurer un, aucun ou tous les fournisseurs. Les missions connexes échoueront simplement en cas de manque de crédits.

### 2.1. Créer le fichier `.env`

Nous supposons que vous avez déjà lu les orientations ci-dessus et vous êtes inscrit auprès du fournisseur pertinent, et avez obtenu les informations d'identification d'authentification requises (API_KEY ou jeton). Dans le cas d'Azure OpenAI, nous supposons que vous avez également un déploiement valide d'un service Azure OpenAI (point de terminaison) avec au moins un modèle GPT déployé pour la complétion de chat.

La prochaine étape consiste à configurer vos **variables d'environnement locales** comme suit :

1. Recherchez le fichier `.env.copy` dans le dossier racine qui doit avoir un contenu comme celui-ci :

   ```bash
   # Fournisseur OpenAI
   OPENAI_API_KEY='<ajoutez votre clé API OpenAI ici>'

   ## Azure OpenAI
   AZURE_OPENAI_API_VERSION='2024-02-01' # La valeur par défaut est définie !
   AZURE_OPENAI_API_KEY='<ajoutez votre clé AOAI ici>'
   AZURE_OPENAI_ENDPOINT='<ajoutez votre point de terminaison de service AOIA ici>'
   AZURE_OPENAI_DEPLOYMENT='<ajoutez le nom de votre modèle de complétion de chat ici>' 
   AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT='<ajoutez le nom de votre modèle de recherche de vecteur ici>'

   ## Hugging Face
   HUGGING_FACE_API_KEY='<ajoutez votre API HuggingFace ou votre jeton ici>'
   ```

2. Copiez ce fichier en `.env` en utilisant la commande ci-dessous. Ce fichier est _gitignore-d_, ce qui permet de protéger les secrets.

   ```bash
   cp .env.copy .env
   ```

3. Remplissez les valeurs (remplacez les espaces réservés du côté droit de `=`) comme décrit dans la section suivante.

3. (Option) Si vous utilisez GitHub Codespaces, vous avez la possibilité de sauvegarder les variables d'environnement en tant que _secrets de Codespaces_ associés à ce référentiel. Dans ce cas, vous n'aurez pas besoin de configurer un fichier .env local. **Cependant, notez que cette option ne fonctionne que si vous utilisez GitHub Codespaces.** Vous devrez toujours configurer le fichier .env si vous utilisez Docker Desktop.

### 2.2. Remplir le fichier `.env`

Jetons un rapide coup d'œil aux noms de variables pour comprendre ce qu'ils représentent :

| Variable  | Description  |
| :--- | :--- |
| HUGGING_FACE_API_KEY | Il s'agit du jeton d'accès utilisateur que vous avez configuré dans votre profil |
| OPENAI_API_KEY | Il s'agit de la clé d'autorisation pour utiliser le service pour les points de terminaison non-Azure OpenAI |
| AZURE_OPENAI_KEY | Il s'agit de la clé d'autorisation pour utiliser ce service |
| AZURE_OPENAI_ENDPOINT | Il s'agit du point de terminaison déployé pour une ressource Azure OpenAI |
| AZURE_OPENAI_DEPLOYMENT | Il s'agit du point de terminaison de déploiement du modèle de _génération de texte_ |
| AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT | Il s'agit du point de terminaison de déploiement du modèle _d'incorporation de texte_ |
| | |

Remarque : Les deux dernières variables Azure OpenAI reflètent un modèle par défaut pour la complétion de chat (génération de texte) et la recherche de vecteurs (incorporation de texte) respectivement. Les instructions pour les configurer seront définies dans les missions pertinentes.

### 2.3 Configurer Azure : depuis le portail

Les valeurs de point de terminaison et de clé Azure OpenAI seront trouvées dans le [portail Azure](https://portal.azure.com?WT.mc_id=academic-105485-koreyst), commençons donc par là.

1. Accédez au [portail Azure](https://portal.azure.com?WT.mc_id=academic-105485-koreyst).
1. Cliquez sur l'option **Keys and Endpoint** dans la barre latérale (menu à gauche).
1. Cliquez sur **Show Keys** - vous devriez voir ce qui suit : KEY 1, KEY 2 et Endpoint.
1. Utilisez la valeur KEY 1 pour AZURE_OPENAI_KEY
1. Utilisez la valeur Endpoint pour AZURE_OPENAI_ENDPOINT

Ensuite, nous avons besoin des points de terminaison pour les modèles spécifiques que nous avons déployés.

1. Cliquez sur l'option **Model deployments** dans la barre latérale (menu à gauche) pour la ressource Azure OpenAI.
1. Dans la page de destination, cliquez sur **Manage Deployments**

Cela vous amènera sur le site Web Azure OpenAI Studio, où nous trouverons les autres valeurs comme décrit ci-dessous.

### 2.4 Configurer Azure : depuis Studio

1. Accédez à [Azure OpenAI Studio](https://oai.azure.com?WT.mc_id=academic-105485-koreyst) **à partir de votre ressource** comme décrit ci-dessus.
1. Cliquez sur l'onglet **Deployments** (barre latérale, gauche) pour afficher les modèles déployés actuellement.
1. Si votre modèle souhaité n'est pas déployé, utilisez **Create new deployment** pour le déployer.
1. Vous aurez besoin d'un modèle de _génération de texte_ - nous recommandons : **gpt-35-turbo**
1. Vous aurez besoin d'un modèle d'_incorporation de texte_ - nous recommandons **text-embedding-ada-002**

Maintenant, mettez à jour les variables d'environnement pour refléter le _nom de déploiement_ utilisé. Cela sera généralement le même que le nom du modèle sauf si vous l'avez changé explicitement. Ainsi, par exemple, vous pourriez avoir :

```bash
AZURE_OPENAI_DEPLOYMENT='gpt-35-turbo'
AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT='text-embedding-ada-002'
```

**N'oubliez pas de sauvegarder le fichier .env une fois terminé**. Vous pouvez maintenant quitter le fichier et revenir aux instructions pour exécuter le carnet. 

### 2.5 Configurer OpenAI : depuis le profil

Votre clé API OpenAI peut être trouvée dans votre [compte OpenAI](https://platform.openai.com/api-keys?WT.mc_id=academic-105485-koreyst). Si vous n'en avez pas, vous pouvez vous inscrire pour un compte et créer une clé API. Une fois que vous avez la clé, vous pouvez l'utiliser pour remplir la variable `OPENAI_API_KEY` dans le fichier `.env`.

### 2.6 Configurer Hugging Face : depuis le profil

Votre jeton Hugging Face peut être trouvé dans votre profil sous [Access Tokens](https://huggingface.co/settings/tokens?WT.mc_id=academic-105485-koreyst). Ne les publiez ni ne les partagez publiquement. Au lieu de cela, créez un nouveau jeton pour une utilisation dans ce projet et copiez-le dans le fichier `.env` sous la variable `HUGGING_FACE_API_KEY`. _Remarque :_ Ce n'est techniquement pas une clé API, mais elle est utilisée pour l'authentification, nous conservons donc cette convention de dénomination pour la cohérence.


Avertissement : La traduction a été effectuée à partir d'un modèle d'IA et peut ne pas être parfaite. Veuillez examiner le résultat et apporter les corrections nécessaires.