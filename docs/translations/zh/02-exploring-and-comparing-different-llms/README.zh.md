# 探索和比较不同的LLMs

[![探索和比较不同的LLMs](./images/02-lesson-banner.png?WT.mc_id=academic-105485-koreyst)](https://learn.microsoft.com/_themes/docs.theme/master/en-us/_themes/global/video-embed.html?id=39aa0f98-826a-4f71-a24d-e888a8e80246?WT.mc_id=academic-105485-koreyst)

> *单击上面的图像以查看本课程的视频*

通过上一课程，我们已经了解到生成式人工智能如何改变技术领域，大型语言模型（LLMs）的工作原理以及像我们的创业公司这样的企业如何将它们应用于他们的用例并发展！在本章中，我们将比较和对比不同类型的大型语言模型（LLMs）以了解它们的优缺点。

我们创业公司旅程的下一步是探索当前LLMs的现状并了解哪些适合我们的用例。

## 介绍

本课程将涵盖：

- 当前LLMs中的不同类型。
- 在Azure中测试、迭代和比较不同的模型。
- 如何部署LLM。

## 学习目标

完成本课程后，您将能够：

- 为您的用例选择正确的模型。
- 了解如何测试、迭代和提高模型的性能。
- 知道企业如何部署模型。

## 了解不同类型的LLMs

LLMs可以根据其架构、训练数据和用例进行多重分类。了解这些差异将有助于我们的创业公司选择适合情况的正确模型，并了解如何测试、迭代和提高性能。

有许多不同类型的LLM模型，您选择的模型取决于您的使用目的、数据、准备支付的金额等等。

根据您的目的，例如文本、音频、视频、图像生成等等，您可能会选择不同类型的模型。

- **音频和语音识别**。对于这个目的，Whisper类型模型是一个很好的选择，因为它们是通用的并针对语音识别。它是在不同的音频上进行训练的，并且可以执行多语言语音识别。在这里了解更多关于[Whisper类型模型](https://platform.openai.com/docs/models/whisper?WT.mc_id=academic-105485-koreyst)的信息。

- **图像生成**。对于图像生成，DALL-E和Midjourney是两个非常知名的选择。DALL-E由Azure OpenAI提供。[在这里阅读有关DALL-E的更多信息](https://platform.openai.com/docs/models/dall-e?WT.mc_id=academic-105485-koreyst)，并在本课程的第9章中了解更多。

- **文本生成**。大多数模型都是针对文本生成进行训练的，您可以从GPT-3.5到GPT-4中选择各种各样的选择。它们的成本不同，其中GPT-4是最昂贵的。值得查看[Azure OpenAI游乐场](https://oai.azure.com/portal/playground?WT.mc_id=academic-105485-koreyst)以评估哪些模型最适合您的需求。

- **多模态**。如果您希望处理多种类型的输入和输出数据，则可以查看[带有视觉的gpt-4 turbo或gpt-4o](https://learn.microsoft.com/azure/ai-services/openai/concepts/models#gpt-4-and-gpt-4-turbo-models?WT.mc_id=academic-105485-koreyst)等模型，这是OpenAI模型的最新版本，它们能够将自然语言处理与视觉理解相结合，通过多模态界面实现交互。

选择模型意味着您可以获得一些基本功能，但这可能不足够。通常，您有公司特定的数据，需要以某种方式告诉LLM。有几种不同的选择来处理这个问题，在即将到来的部分中会更多地介绍。

### 基础模型与LLMs

术语“基础模型”是由斯坦福大学的研究人员[创造的](https://arxiv.org/abs/2108.07258?WT.mc_id=academic-105485-koreyst)，并定义为遵循某些标准的AI模型，例如：

- **它们使用无监督学习或自我监督学习进行训练**，这意味着它们是在未标记的多模态数据上进行训练的，并且它们不需要人类注释或标记数据进行训练过程。
- **它们是非常大的模型**，基于训练在数十亿个参数上的非常深的神经网络。
- **它们通常旨在作为其他模型的“基础”**，这意味着它们可以用作其他模型的起点，可以通过微调来完成。

![基础模型与LLMs](./images/FoundationModel.png?WT.mc_id=academic-105485-koreyst)

图像来源：[基础模型和大型语言模型的基本指南 | 由Babar M Bhatti | 中号](https://thebabar.medium.com/essential-guide-to-foundation-models-and-large-language-models-27dab58f7404)

为了进一步澄清这一区别，让我们以ChatGPT为例。为了构建ChatGPT的第一个版本，OpenAI使用了一个名为GPT-3.5的模型作为基础模型。这意味着OpenAI使用了一些聊天特定的数据来创建GPT-3.5的调整版本，该版本专门用于在会话场景中表现良好，例如聊天机器人。

![基础模型](./images/Multimodal.png?WT.mc_id=academic-105485-koreyst)

图像来源：[2108.07258.pdf(arxiv.org)](https://arxiv.org/pdf/2108.07258.pdf?WT.mc_id=academic-105485-koreyst)

### 开源与专有模型

分类LLMs的另一种方法是它们是开源还是专有模型。

开源模型是向公众提供的模型，任何人都可以使用。它们通常由创建它们的公司或研究社区提供。这些模型允许进行检查、修改和定制，以适应LLMs的各种用例。但是，它们并不总是针对生产使用进行优化，并且可能不像专有模型那样高效。此外，开源模型的资金可能有限，它们可能不会长期维护，或者可能不会更新最新的研究。流行的开源模型的例子包括[Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html?WT.mc_id=academic-105485-koreyst)、[Bloom](https://sapling.ai/llm/bloom?WT.mc_id=academic-105485-koreyst)和[LLaMA](https://sapling.ai/llm/llama?WT.mc_id=academic-105485-koreyst)。

专有模型是由公司拥有的模型，不向公众提供。这些模型通常针对生产使用进行优化。但是，它们不允许进行检查、修改或定制以适应不同的用例。此外，它们并不总是免费提供，并且可能需要订阅或支付才能使用。此外，用户无法控制用于训练模型的数据，这意味着他们应该信任模型所有者确保数据隐私和AI的负责使用。流行的专有模型包括[OpenAI模型](https://platform.openai.com/docs/models/overview?WT.mc_id=academic-105485-koreyst)、[Google Bard](https://sapling.ai/llm/bard?WT.mc_id=academic-105485-koreyst)或[Claude 2](https://www.anthropic.com/index/claude-2?WT.mc_id=academic-105485-koreyst)。

### 嵌入与图像生成与文本和代码生成

LLMs也可以按其生成的输出进行分类。

嵌入是一组可以将文本转换为数字形式的模型，称为嵌入，这是输入文本的数字表示形式。嵌入使机器更容易理解单词或句子之间的关系，并且可以作为其他模型的输入，例如具有更好数值数据性能的分类模型或聚类模型。嵌入模型通常用于迁移学习，其中为代理任务构建模型，有大量数据可用，然后重用模型权重（嵌入）用于其他下游任务。这个类别的一个例子是[OpenAI嵌入](https://platform.openai.com/docs/models/embeddings?WT.mc_id=academic-105485-koreyst)。

![嵌入](./images/Embedding.png?WT.mc_id=academic-105485-koreyst)

图像生成模型是生成图像的模型。这些模型通常用于图像编辑、图像合成和图像转换。图像生成模型通常在大型图像数据集上进行训练，例如[LAION-5B](https://laion.ai/blog/laion-5b/?WT.mc_id=academic-105485-koreyst)，可以用于生成新图像或使用修补、超分辨率和着色技术编辑现有图像。例子包括[DALL-E-3](https://openai.com/dall-e-3?WT.mc_id=academic-105485-koreyst)和[Stable Diffusion models](https://github.com/Stability-AI/StableDiffusion?WT.mc_id=academic-105485-koreyst)。

![图像生成](./images/Image.png?WT.mc_id=academic-105485-koreyst)

文本和代码生成模型是生成文本或代码的模型。这些模型通常用于文本摘要、翻译和问答。文本生成模型通常在大型文本数据集上进行训练，例如[BookCorpus](https://www.cv-foundation.org/openaccess/content_iccv_2015/html/Zhu_Aligning_Books_and_ICCV_2015_paper.html?WT.mc_id=academic-105485-koreyst)，可以用于生成新文本或回答问题。代码生成模型，如[CodeParrot](https://huggingface.co/codeparrot?WT.mc_id=academic-105485-koreyst)，通常在大型代码数据集上进行训练，例如GitHub，可以用于生成新代码或修复现有代码中的错误。

 ![文本和代码生成](./images/Text.png?WT.mc_id=academic-105485-koreyst)

### 编码器-解码器与仅解码器

为了讨论LLMs的不同架构类型，让我们使用一个类比。

想象一下，您的经理给您一个编写学生测验的任务。您有两个同事；一个负责创建内容，另一个负责审查。

内容创建者就像一个仅解码器模型，他可以查看主题并查看您已经编写的内容，然后可以根据此编写课程。他非常擅长编写引人入胜和信息丰富的内容，但他并不擅长理解主题和学习目标。一些Decoder模型的例子是GPT系列模型，例如GPT-3。

审阅者就像一个仅编码器模型，他查看编写的课程和答案，注意它们之间的关系并理解上下文，但不擅长生成内容。仅编码器模型的一个例子是BERT。

想象一下，我们还可以有一个人来创建和审阅测验，这就是编码器-解码器模型。一些例子是BART和T5。

### 服务与模型

现在，让我们谈谈服务和模型之间的区别。服务是由云服务提供商提供的产品，通常是模型、数据和其他组件的组合。模型是服务的核心组件，通常是基础模型，例如LLMs。

服务通常针对生产使用进行优化，并且通常比模型更易于使用，通过图形用户界面。但是，服务并不总是免费提供，并且可能需要订阅或支付才能使用，以换取利用服务所有者的设备和资源、优化费用和轻松扩展。服务的一个例子是[Azure OpenAI服务](https://learn.microsoft.com/azure/ai-services/openai/overview?WT.mc_id=academic-105485-koreyst)，它提供按使用量付费的价格计划，这意味着用户按照使用服务的程度进行比例收费。此外，Azure OpenAI服务还提供企业级安全性和负责任的AI框架，以提高模型的能力。

模型只是神经网络，具有参数、权重和其他参数。允许公司在本地运行，但需要购买设备、构建结构以扩展并购买许可证或使用开源模型。像LLaMA这样的模型可供使用，需要计算能力来运行模型。

## 如何测试和迭代不同的模型以了解在Azure上的性能

一旦我们的团队探索了当前LLMs的现状，并确定了一些适合其场景的良好候选项，下一步是在其数据和工作负载上对其进行测试。这是一个迭代过程，通过实验和度量来完成。我们在前面的段落中提到的大多数模型（OpenAI模型、Llama2等开源模型和Hugging Face transformers）都可以在Azure AI Studio的[Model Catalog](https://learn.microsoft.com/azure/ai-studio/how-to/model-catalog-overview?WT.mc_id=academic-105485-koreyst)中找到。

[Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/what-is-ai-studio?WT.mc_id=academic-105485-koreyst)是一个云平台，专为开发人员构建生成式AI应用程序并管理整个开发生命周期而设计的，从实验到评估，将所有Azure AI服务结合成一个方便的GUI。Azure AI Studio中的Model Catalog使用户能够：

- 在目录中找到感兴趣的基础模型-专有或开源，通过任务、许可证或名称进行筛选。为了提高可搜索性，模型被组织成集合，如Azure OpenAI集合、Hugging Face集合等。

![模型目录](./images/AzureAIStudioModelCatalog.png?WT.mc_id=academic-105485-koreyst)

- 查看模型卡，包括详细的用途和训练数据说明、代码示例和内部评估库中的评估结果。

![模型卡](./images/ModelCard.png?WT.mc_id=academic-105485-koreyst)

- 比较行业中可用的模型和数据集的基准测试，以评估哪一个符合业务场景，通过[模型基准测试](https://learn.microsoft.com/azure/ai-studio/how-to/model-benchmarks?WT.mc_id=academic-105485-koreyst)窗格。

![模型基准测试](./images/ModelBenchmarks.png
对于用户的期望，答案将是什么。在这种情况下，如果提示只包括一个示例，则我们谈论“单次”学习，如果它包括多个示例，则为“少量学习”。具有上下文的提示工程是启动最具成本效益的方法。### 检索增强生成（RAG）LLM存在一个限制，即它们只能使用在其培训期间使用过的数据来生成答案。这意味着它们不知道在培训过程之后发生的任何事实，并且无法访问非公共信息（如公司数据）。这可以通过RAG克服，该技术以文档块的形式增强提示外部数据，考虑提示长度限制。这得到支持矢量数据库工具（如[Azure Vector Search](https://learn.microsoft.com/azure/search/vector-search-overview?WT.mc_id=academic-105485-koreyst)），它从各种预定义数据源中检索有用的块并将它们添加到提示上下文中。当企业没有足够的数据，足够的时间或资源来微调LLM，但仍希望在特定工作负载上提高性能并降低虚构，即现实或有害内容的风险时，这种技术非常有用。### 微调模型微调是一种利用转移学习“适应”模型到下游任务或解决特定问题的过程。与少量学习和RAG不同，它会生成一个新模型，具有更新的权重和偏差。它需要一组训练示例，包括单个输入（提示）及其相关输出（完成）。如果：- **使用微调模型**。企业希望使用微调能力较弱的模型（如嵌入模型）而不是高性能模型，从而实现更具成本效益和快速的解决方案。- **考虑延迟**。延迟对于特定用例很重要，因此不可能使用非常长的提示或应该从模型中学习的示例数量不符合提示长度限制。- **保持最新状态**。企业拥有大量高质量数据和地面真相标签以及在时间上保持这些数据最新所需的资源。### 训练模型从头开始训练LLM无疑是采用的最困难和最复杂的方法，需要大量的数据，熟练的资源和适当的计算能力。只有在业务具有特定于域的用例和大量领域中心数据的情况下，才应考虑这个选项。## 知识检查什么是改善LLM完成结果的好方法？ 1.具有上下文的提示工程1.RAG 1.微调模型A：3，如果您有时间和资源以及高质量数据，微调是保持最新状态的更好选择。但是，如果您正在寻求改进并且时间不足，则值得首先考虑RAG。## 🚀挑战更多了解如何[使用RAG](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview?WT.mc_id=academic-105485-koreyst)为您的业务。## 伟大的工作，继续学习完成本课程后，请查看我们的[生成AI学习集合](https://aka.ms/genai-collection?WT.mc_id=academic-105485-koreyst)以继续提升您的生成AI知识水平！前往第3课，我们将看看如何[负责任地使用生成AI构建](../03-using-generative-ai-responsibly/README.md?WT.mc_id=academic-105485-koreyst)！


免责声明：本翻译是由AI模型翻译的原始版本，可能不完美。请检查输出并进行必要的更正。