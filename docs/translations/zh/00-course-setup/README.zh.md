# 开始学习这门课程

我们非常期待你开始学习这门课程，并看看你将用生成式 AI 构建什么样的东西！

为了确保你的成功，本页概述了设置步骤、技术要求以及在需要帮助时获取帮助的位置。

## 设置步骤

为了开始学习这门课程，你需要完成以下步骤。

### 1. Fork 这个 Repo

将此 Repo 克隆到你自己的 GitHub 帐户中，以便能够更改任何代码并完成挑战。你也可以给这个 Repo 点个赞（🌟），以便更容易地找到它和相关的 Repo。

### 2. 创建 codespace

为了避免在运行代码时出现任何依赖性问题，我们建议在 [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) 中运行此课程。

这可以通过在你的 fork 版本中选择“Code”选项，然后选择 **Codespaces** 选项来创建。

![Dialog showing buttons to create a codespace](./images/who-will-pay.webp?WT.mc_id=academic-105485-koreyst)

### 3. 存储你的 API 密钥

在构建任何类型的应用程序时，保持 API 密钥的安全性是很重要的。我们建议不要直接将任何 API 密钥存储在你的代码中。将这些详细信息提交到公共存储库中可能会导致安全问题，甚至会导致不必要的成本，如果被恶意行为者使用。

## 如何在本地计算机上运行

要在本地计算机上运行代码，你需要安装一些版本的 [Python](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)。

然后，你需要克隆它：

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

一旦你检查好了所有内容，你就可以开始了！

### 安装 Miniconda（可选步骤）

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) 是一个轻量级安装程序，用于安装 [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst)、Python 以及一些包。
Conda 本身是一个包管理器，可以轻松设置和切换不同的 Python [**虚拟环境**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) 和包。它还可以帮助安装不可通过 `pip` 获取的包。

你可以按照 [MiniConda 安装指南](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) 进行设置。

安装 Miniconda 后，你需要克隆 [存储库](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst)（如果你还没有）。

接下来，你需要创建一个虚拟环境。为此，使用 Conda，继续创建一个新的环境文件（_environment.yml_）。如果你正在使用 Codespaces 跟随操作，请在 `.devcontainer` 目录中创建此文件，即 `.devcontainer/environment.yml`。

使用下面的代码片段填充你的环境文件：

```yml
name: <environment-name>
channels:
 - defaults
dependencies:
- python=<python-version>
- openai
- python-dotenv
```

环境文件指定了我们需要的依赖项。`<environment-name>` 是你想要用于 Conda 环境的名称，`<python-version>` 是你想要使用的 Python 版本，例如 `3` 是 Python 的最新主要版本。

完成后，你可以在命令行/终端中运行下面的命令来创建你的 Conda 环境：

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer 子路径仅适用于 Codespace 设置
conda activate ai4beg
```

如果遇到任何问题，请参考 [Conda 环境指南](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst)。

### 使用带有 Python 支持扩展的 Visual Studio Code

我们建议使用安装了 [Python 支持扩展](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) 的 [Visual Studio Code（VS Code）](http://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) 编辑器来完成此课程。然而，这更多是一个建议，而不是一个明确的要求。

> **注意**：通过在 VS Code 中打开课程存储库，你可以选择在容器内设置项目。这是因为在课程存储库中找到的 [特殊 `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) 目录。稍后会详细介绍这个。

> **注意**：一旦你克隆并在 VS Code 中打开目录，它将自动建议你安装 Python 支持扩展。

> **注意**：如果 VS Code 建议你在容器中重新打开存储库，请拒绝此请求，以便使用本地安装的 Python 版本。

### 在浏览器中使用 Jupyter

你也可以使用 [Jupyter 环境](https://jupyter.org?WT.mc_id=academic-105485-koreyst) 直接在浏览器中工作。经典 Jupyter 和 [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) 都提供了相当愉悦的开发环境，具有自动完成、代码高亮等功能。

要在本地启动 Jupyter，请转到终端/命令行，导航到课程目录，然后执行：

```bash
jupyter notebook
```

或者

```bash
jupyterhub
```

这将启动一个 Jupyter 实例，访问它的 URL 将显示在命令行窗口中。

一旦你访问了 URL，你应该会看到课程大纲，并能够导航到任何 `*.ipynb` 文件。例如，`08-building-search-applications/python/oai-solution.ipynb`。

### 在容器中运行

在计算机或 Codespace 上设置所有内容的替代方法是使用 [容器](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst)。课程存储库中的特殊 `.devcontainer` 文件夹使得 VS Code 可以在容器中设置项目。在 Codespaces 之外，这将需要安装 Docker，并且说实话，它需要一些工作，因此我们建议仅限有使用容器经验的人使用此方法。

在使用 GitHub Codespaces 时保持 API 密钥安全的最佳方法之一是使用 Codespace Secrets。请按照 [Codespaces secrets 管理](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) 指南了解更多信息。

## 课程和技术要求

本课程有 6 个概念课程和 6 个编码课程。

对于编码课程，我们使用 Azure OpenAI 服务。你需要访问 Azure OpenAI 服务并获得一个 API 密钥才能运行此代码。你可以通过 [完成此申请](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) 来获得访问权限。

在等待处理申请的过程中，每个编码课程都包括一个 `README.md` 文件，你可以在其中查看代码和输出。

## 第一次使用 Azure OpenAI 服务

如果这是你第一次使用 Azure OpenAI 服务，请按照这个指南 [创建和部署 Azure OpenAI 服务资源](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)。

## 第一次使用 OpenAI API

如果这是你第一次使用 OpenAI API，请按照指南了解如何 [创建和使用接口](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)。

## 与其他学习者见面

我们在我们的官方 [AI Community Discord 服务器](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) 中创建了频道，以便与其他学习者见面。这是与其他志同道合的企业家、建筑师、学生以及任何想在生成式 AI 中升级的人建立网络的绝佳方式。

[![Join discord channel](https://dcbadge.vercel.app/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

项目团队也将在这个 Discord 服务器上帮助任何学习者。

## 贡献

这门课程是一个开源的倡议。如果你看到需要改进的地方或问题，请创建一个 [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) 或记录一个 [GitHub 问题](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst)。

项目团队将跟踪所有贡献。贡献到开源是建立你的生成式 AI 职业生涯的一个惊人的方式。

大多数贡献需要你同意贡献者许可协议 (CLA)，声明你有权利并实际上授予我们使用你的贡献的权利。有关详细信息，请访问 [CLA，贡献者许可协议网站](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst)。

重要提示：在翻译此存储库中的文本时，请确保不要使用机器翻译。我们将通过社区验证翻译，请仅在你精通的语言中自愿进行翻译。

当你提交拉取请求时，CLA-bot 将自动确定是否需要提供 CLA，并适当地装饰 PR（例如，标签、评论）。只需按照机器人提供的说明即可。你只需要在使用我们的 CLA 的所有存储库中完成一次。

此项目已采用 [Microsoft 开源行为准则](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst)。有关更多信息，请阅读行为准则 FAQ 或通过 [电子邮件 opencode](opencode@microsoft.com) 与任何其他问题或评论联系。

## 让我们开始吧

现在，你已经完成了完成此课程所需的步骤，让我们通过 [介绍生成式 AI 和 LLMs](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) 来开始吧。


免责声明：本翻译是由AI模型翻译的，可能不完美。请查看输出并进行必要的更正。