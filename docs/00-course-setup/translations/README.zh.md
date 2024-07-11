# 开始这门课程

我们非常期待你开始这门课程，看看你会因生成式人工智能而激发出什么样的灵感！

为了确保你的成功，本页面概述了设置步骤、技术要求以及在需要帮助时获取帮助的位置。

## 设置步骤

要开始学习这门课程，您需要完成以下步骤。

### 1. 分叉此存储库

将[Fork此整个存储库](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst)到您自己的GitHub帐户中，以便能够更改任何代码并完成挑战。您还可以[为此存储库加星（🌟）](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst)，以更轻松地找到它和相关的存储库。

### 2. 创建codespace

为了避免在运行代码时出现任何依赖性问题，我们建议在[GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst)中运行此课程。

这可以通过选择您分叉的版本的“Code”选项，然后选择**Codespaces**选项来创建。

![对话框显示创建codespace的按钮](./images/who-will-pay.webp?WT.mc_id=academic-105485-koreyst)

### 3. 存储您的API密钥

在构建任何类型的应用程序时，保护API密钥的安全性非常重要。我们建议不要直接将任何API密钥存储在代码中。将这些详细信息提交到公共存储库可能会导致安全问题，甚至会产生不必要的成本，如果被不良行为者使用。

## 如何在本地计算机上运行

要在本地计算机上运行代码，您需要安装某个版本的[Python](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)。

然后，您需要克隆它以使用存储库：

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

一旦您已经检查好了所有内容，就可以开始了！

### 安装Miniconda（可选步骤）

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst)是一个轻量级安装程序，用于安装[Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst)、Python以及一些软件包。
Conda本身是一个软件包管理器，它使设置和在不同的Python [**虚拟环境**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst)和软件包之间切换变得容易。它还可以方便地安装不可通过`pip`获得的软件包。

您可以按照[MiniConda安装指南](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst)进行设置。

安装Miniconda后，您需要克隆[存储库](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst)（如果您尚未这样做）

接下来，您需要创建一个虚拟环境。要使用Conda完成此操作，请继续并创建一个新的环境文件（_environment.yml_）。如果您使用Codespaces跟随本教程，请在`.devcontainer`目录中创建此文件，因此为`.devcontainer/environment.yml`。

继续并使用下面的片段填充您的环境文件：

```yml
name: <environment-name>
channels:
 - defaults
dependencies:
- python=<python-version>
- openai
- python-dotenv
```

环境文件指定了我们需要的依赖项。`<environment-name>`是您要用于Conda环境的名称，`<python-version>`是您要使用的Python版本，例如，`3`是Python的最新主要版本。

完成后，您可以通过在命令行/终端中运行以下命令来创建您的Conda环境

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer子路径仅适用于Codespace设置
conda activate ai4beg
```

如果遇到任何问题，请参阅[Conda环境指南](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst)。

### 使用带有Python支持扩展的Visual Studio Code

我们建议使用[Visual Studio Code（VS Code）](http://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst)编辑器与安装了[Python支持扩展](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst)的本课程一起使用。然而，这更多的是建议而不是明确的要求。

> **注意**：通过在VS Code中打开课程存储库，您可以选择在容器中设置项目。这是因为在课程存储库中找到的[特殊`.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst)目录。稍后会详细介绍。

> **注意**：一旦您克隆并在VS Code中打开目录，它将自动建议您安装Python支持扩展。

> **注意**：如果VS Code建议您重新在容器中打开存储库，请拒绝此请求，以便使用本地安装的Python版本。

### 在浏览器中使用Jupyter

您还可以使用[Jupyter环境](https://jupyter.org?WT.mc_id=academic-105485-koreyst)直接在浏览器中处理项目。经典的Jupyter和[Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst)都提供了非常愉快的开发环境，具有自动完成、代码高亮等功能。

要在本地启动Jupyter，请转到终端/命令行，导航到课程目录，并执行：

```bash
jupyter notebook
```

或

```bash
jupyterhub
```

这将启动一个Jupyter实例，可以在命令行窗口中显示访问它的URL。

一旦访问URL，您应该会看到课程大纲，并能够导航到任何`*.ipynb`文件。例如，`08-building-search-applications/python/oai-solution.ipynb`。

### 在容器中运行

在计算机或Codespace上设置所有内容的替代方法是使用[容器](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst)。课程存储库中的特殊`.devcontainer`文件夹使得VS Code能够在容器中设置项目。在Codespaces之外，这将需要安装Docker，并且实际上需要一些工作，因此我们建议仅对有经验的容器工作人员使用此方法。

在使用GitHub Codespaces时保护API密钥的最佳方法之一是使用Codespace Secrets。请按照[Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst)指南了解更多信息。

## 课程和技术要求

该课程有6个概念课程和6个编码课程。

对于编码课程，我们使用Azure OpenAI服务。您需要访问Azure OpenAI服务并获得API密钥才能运行此代码。您可以通过[完成此申请](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst)来获得访问权限。

在等待处理申请的同时，每个编码课程还包括一个`README.md`文件，您可以在其中查看代码和输出。

## 首次使用Azure OpenAI服务

如果这是您第一次使用Azure OpenAI服务，请按照此指南了解如何[创建和部署Azure OpenAI服务资源。](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## 首次使用OpenAI API

如果这是您第一次使用OpenAI API，请按照有关[创建和使用接口的指南](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)进行操作。

## 遇见其他学习者

我们在我们的官方[AI Community Discord服务器](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)中创建了频道，以满足其他学习者。这是与其他志同道合的企业家、建筑师、学生以及任何想在生成式人工智能领域升级的人建立网络的好方法。

[![加入discord频道](https://dcbadge.vercel.app/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

项目团队也将在此Discord服务器上帮助任何学习者。

## 贡献

本课程是一个开源计划。如果您发现有改进或问题，请创建[Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst)或记录[GitHub问题](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst)。

项目团队将跟踪所有贡献。为开源做贡献是在生成式人工智能领域建立职业生涯的绝佳方式。

大多数贡献需要您同意参与者许可协议（CLA），声明您拥有权利并确实授予我们使用您的贡献的权利。有关详细信息，请访问[CLA，参与者许可协议网站](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst)。

重要提示：在翻译此存储库中的文本时，请确保不使用机器翻译。我们将通过社区验证翻译，因此请仅在您精通的语言中自愿进行翻译。

当您提交拉取请求时，CLA机器人将自动确定您是否需要提供CLA，并适当地装饰PR（例如，标签、评论）。只需按照机器人提供的说明即可。您只需要在使用我们的CLA的所有存储库中执行一次此操作。

本项目已采用[Microsoft开源行为准则](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst)。有关更多信息，请阅读行为准则FAQ或通过[电子邮件opencode](opencode@microsoft.com)与我们联系，以获得任何其他问题或评论。

## 让我们开始吧

现在，您已经完成了完成本课程所需的步骤，请通过获取[生成式AI和LLMs的介绍](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst)来开始。


免责声明：该翻译是由人工智能模型翻译的原始文本，可能不完美。请查看输出并进行必要的更正。