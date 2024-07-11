# 设置您的开发环境

我们使用带有通用运行时的[开发容器](https://containers.dev?WT.mc_id=academic-105485-koreyst)来设置这个仓库和课程，该容器可以支持Python3、.NET、Node.js和Java开发。相关配置在该存储库根目录下的`.devcontainer/`文件夹中的`devcontainer.json`文件中定义。

要激活dev容器，请在[GitHub Codespaces](https://docs.github.com/en/codespaces/overview?WT.mc_id=academic-105485-koreyst)(云托管运行时)或[Docker Desktop](https://docs.docker.com/desktop/?WT.mc_id=academic-105485-koreyst)(本地设备托管运行时)中启动它。阅读[此文档](https://code.visualstudio.com/docs/devcontainers/containers?WT.mc_id=academic-105485-koreyst)以了解有关VS Code中dev容器如何工作的更多详细信息。

> [!提示]  
> 我们建议使用GitHub Codespaces快速启动并以最小的努力开始。它为个人帐户提供慷慨的[免费使用配额](https://docs.github.com/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts?WT.mc_id=academic-105485-koreyst)。配置[超时](https://docs.github.com/codespaces/setting-your-user-preferences/setting-your-timeout-period-for-github-codespaces?WT.mc_id=academic-105485-koreyst)以停止或删除不活动的codespaces以最大化您的配额使用。

## 1. 执行任务

每个课程都会提供可选的任务，这些任务可能提供一个或多个编程语言，包括：Python、.NET/C#、Java和JavaScript/TypeScript。本节提供与执行这些任务相关的一般指导。

### 1.1 Python任务

Python任务提供为应用程序(`.py`文件)或Jupyter笔记本(`.ipynb`文件)。

- 要运行笔记本，请在Visual Studio Code中打开它，然后单击右上角的“选择内核”并选择显示的默认Python 3选项。现在，您可以运行所有内容以执行笔记本。
- 要从命令行运行Python应用程序，请按照任务特定的说明确保您选择了正确的文件并提供所需的参数。

## 2. 配置提供程序

任务**可能**还可以设置为通过支持的服务提供程序（如OpenAI、Azure或Hugging Face）与一个或多个大型语言模型（LLM）部署一起使用。这些提供了我们可以使用正确的凭据（API密钥或令牌）以编程方式访问的_托管端点_（API）。在本课程中，我们讨论这些提供程序：

- [OpenAI](https://platform.openai.com/docs/models?WT.mc_id=academic-105485-koreyst)具有包括核心GPT系列在内的多种模型。
- [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/?WT.mc_id=academic-105485-koreyst)用于具有企业就绪性的OpenAI模型
- [Hugging Face](https://huggingface.co/docs/hub/index?WT.mc_id=academic-105485-koreyst)用于开源模型和推理服务器

**您将需要使用自己的帐户进行这些练习**。任务是可选的，因此您可以根据自己的兴趣选择设置一个、全部或不设置提供程序。一些注册指南：

| 注册 | 成本 | API密钥 | Playground | 注释 |
|:---|:---|:---|:---|:---|
| [OpenAI](https://platform.openai.com/signup?WT.mc_id=academic-105485-koreyst)| [价格](https://openai.com/pricing#language-models?WT.mc_id=academic-105485-koreyst)| [基于项目](https://platform.openai.com/api-keys?WT.mc_id=academic-105485-koreyst) | [无代码，Web](https://platform.openai.com/playground?WT.mc_id=academic-105485-koreyst) | 多个模型可用 |
| [Azure](https://aka.ms/azure/free?WT.mc_id=academic-105485-koreyst)| [价格](https://azure.microsoft.com/pricing/details/cognitive-services/openai-service/?WT.mc_id=academic-105485-koreyst)| [SDK快速入门](https://learn.microsoft.com/azure/ai-services/openai/quickstart?WT.mc_id=academic-105485-koreyst)| [Studio快速入门](https://learn.microsoft.com/azure/ai-services/openai/quickstart?WT.mc_id=academic-105485-koreyst) |  [必须提前申请访问权限](https://learn.microsoft.com/azure/ai-services/openai/?WT.mc_id=academic-105485-koreyst)|
| [Hugging Face](https://huggingface.co/join?WT.mc_id=academic-105485-koreyst) | [价格](https://huggingface.co/pricing) | [访问令牌](https://huggingface.co/docs/hub/security-tokens?WT.mc_id=academic-105485-koreyst) | [Hugging Chat](https://huggingface.co/chat/?WT.mc_id=academic-105485-koreyst)| [Hugging Chat有限的模型](https://huggingface.co/chat/models?WT.mc_id=academic-105485-koreyst) |
| | | | | |

按照下面的说明来_配置_此存储库以与不同的提供程序一起使用。需要特定提供程序的任务将在其文件名中包含以下标记之一：
- `aoai`-需要Azure OpenAI端点、密钥
- `oai`-需要OpenAI端点、密钥
- `hf`-需要Hugging Face令牌

您可以配置一个、无或所有提供程序。相关任务将简单地因缺少凭据而出现错误。

### 2.1. 创建`.env`文件

我们假设您已经阅读了上面的指导并与相关提供程序进行了注册，并获得了所需的身份验证凭据（API_KEY或令牌）。在Azure OpenAI的情况下，我们假设您还拥有一个有效的Azure OpenAI服务部署（端点），并且至少部署了一个GPT模型以进行聊天完成。

下一步是按如下方式配置您的**本地环境变量**：

1. 在根文件夹中查找`.env.copy`文件，其内容应如下所示：

   ```bash
   # OpenAI Provider
   OPENAI_API_KEY='<add your OpenAI API key here>'

   ## Azure OpenAI
   AZURE_OPENAI_API_VERSION='2024-02-01' # Default is set!
   AZURE_OPENAI_API_KEY='<add your AOAI key here>'
   AZURE_OPENAI_ENDPOINT='<add your AOIA service endpoint here>'
   AZURE_OPENAI_DEPLOYMENT='<add your chat completion model name here>' 
   AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT='<add your embeddings model name here>'

   ## Hugging Face
   HUGGING_FACE_API_KEY='<add your HuggingFace API or token here>'
   ```

2. 使用以下命令将该文件复制到`.env`。该文件是_gitignore-d_，可保护秘密。

   ```bash
   cp .env.copy .env
   ```

3. 根据下一节中的说明填写值（替换等号右侧的占位符）。

3. (可选) 如果您使用GitHub Codespaces，则可以将环境变量保存为与此存储库关联的_Codespaces secrets_。在这种情况下，您将不需要设置本地.env文件。**但是，请注意，此选项仅适用于使用GitHub Codespaces的情况。**如果您使用Docker Desktop，则仍需要设置.env文件。

### 2.2. 填充`.env`文件

让我们快速查看变量名称，以了解它们代表什么：

| 变量 | 描述 |
| :--- | :--- |
| HUGGING_FACE_API_KEY | 这是您在配置文件中设置的用户访问令牌 |
| OPENAI_API_KEY | 这是用于非Azure OpenAI端点使用服务的授权密钥 |
| AZURE_OPENAI_KEY | 这是用于使用该服务的授权密钥 |
| AZURE_OPENAI_ENDPOINT | 这是Azure OpenAI资源的部署端点 |
| AZURE_OPENAI_DEPLOYMENT | 这是_text generation_模型部署端点 |
| AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT | 这是_text embeddings_模型部署端点 |
| | |

注意：Azure OpenAI的最后两个变量反映了默认的聊天完成（文本生成）和向量搜索（嵌入）模型。相关任务的设置说明将在相应的任务中定义。

### 2.3 从门户配置Azure

Azure OpenAI端点和密钥值将在[Azure门户](https://portal.azure.com?WT.mc_id=academic-105485-koreyst)中找到，因此让我们从那里开始。

1. 转到[Azure门户](https://portal.azure.com?WT.mc_id=academic-105485-koreyst)
1. 单击侧边栏（左侧菜单）中的**密钥和端点**选项。
1. 单击**显示密钥**-您应该看到以下内容：KEY 1、KEY 2和Endpoint。
1. 使用KEY 1值作为AZURE_OPENAI_KEY
1. 使用Endpoint值作为AZURE_OPENAI_ENDPOINT

接下来，我们需要特定模型的端点。

1. 单击Azure OpenAI资源中的**模型部署**选项卡（侧边栏，左侧）。
1. 在目标页面中，单击**管理部署**

这将带您转到Azure OpenAI Studio网站，在该网站中，我们将根据以下说明找到其他值。

### 2.4 从Studio配置Azure

1. 从上面的资源中导航到[Azure OpenAI Studio](https://oai.azure.com?WT.mc_id=academic-105485-koreyst)。
1. 单击**部署**选项卡（侧边栏，左侧）以查看当前部署的模型。
1. 如果未部署所需的模型，请使用**创建新部署**进行部署。
1. 您将需要一个_text-generation_模型-我们推荐：**gpt-35-turbo**
1. 您将需要一个_text-embedding_模型-我们推荐**text-embedding-ada-002**

现在更新环境变量以反映所使用的_Deployment name_。这通常与模型名称相同，除非您明确更改了它。因此，例如，您可能有：

```bash
AZURE_OPENAI_DEPLOYMENT='gpt-35-turbo'
AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT='text-embedding-ada-002'
```

**完成后不要忘记保存.env文件**。现在您可以退出文件并返回运行笔记本的说明。

### 2.5 从配置文件配置OpenAI

您的OpenAI API密钥可以在您的[OpenAI帐户](https://platform.openai.com/api-keys?WT.mc_id=academic-105485-koreyst)中找到。如果没有，请注册一个帐户并创建API密钥。获得密钥后，您可以将其用于填充`.env`文件中的`OPENAI_API_KEY`变量。

### 2.6 从配置文件配置Hugging Face

您的Hugging Face令牌可以在[Access Tokens](https://huggingface.co/settings/tokens?WT.mc_id=academic-105485-koreyst)下的个人资料中找到。请勿公开或共享这些令牌。相反，为此项目使用创建新令牌，并将其复制到`.env`文件中的`HUGGING_FACE_API_KEY`变量下。_注意：这在技术上不是API密钥，但用于身份验证，因此我们为了一致性保持了该命名约定。_


免责声明：该翻译是由AI模型翻译的，可能不完美。请查看输出并进行必要的更正。