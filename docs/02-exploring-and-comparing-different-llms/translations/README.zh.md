# 探索和比较不同的LLMs

[![探索和比较不同的LLMs](./images/02-lesson-banner.png?WT.mc_id=academic-105485-koreyst)](https://learn.microsoft.com/_themes/docs.theme/master/en-us/_themes/global/video-embed.html?id=39aa0f98-826a-4f71-a24d-e888a8e80246?WT.mc_id=academic-105485-koreyst)

> *点击上面的图像查看此课程的视频*

通过前面的课程，我们已经了解到生成式AI如何改变技术领域，大型语言模型（LLMs）的工作原理以及像我们这样的初创企业如何应用它们来实现其用例并实现增长！在本章中，我们将比较和对比不同类型的大型语言模型（LLMs），以了解它们的优缺点。

我们初创企业旅程的下一步是探索当前的LLMs景观，并了解哪些适合我们的用例。

## 介绍

本课将涵盖：

- 当前景观中不同类型的LLMs。
- 在Azure中测试，迭代和比较不同的模型。
- 如何部署LLM。

## 学习目标

完成本课后，您将能够：

- 为您的用例选择正确的模型。
- 理解如何测试，迭代和提高模型的性能。
- 了解企业如何部署模型。

## 了解不同类型的LLMs

LLMs可以基于其架构，训练数据和用例进行多种分类。了解这些差异将有助于我们的初创企业选择适合该场景的正确模型，并了解如何测试，迭代和提高性能。

有许多不同类型的LLM模型，您选择的模型取决于您想要将其用于的内容，您的数据，您准备支付的金额等。

根据您的用途是否为文本，音频，视频，图像生成等，您可能会选择不同类型的模型。

- **音频和语音识别**。对于此目的，Whisper类型的模型是一个很好的选择，因为它们是通用的并且旨在进行语音识别。它在多样的音频上进行了训练，并且可以执行多语言语音识别。在此处了解更多关于[Whisper类型的模型](https://platform.openai.com/docs/models/whisper?WT.mc_id=academic-105485-koreyst)的信息。

- **图像生成**。对于图像生成，DALL-E和Midjourney是两个非常知名的选择。 DALL-E由Azure OpenAI提供。在此处[阅读有关DALL-E的更多信息](https://platform.openai.com/docs/models/dall-e?WT.mc_id=academic-105485-koreyst)，并在本课程的第9章中了解更多信息。

- **文本生成**。大多数模型都是针对文本生成进行训练的，您可以从GPT-3.5到GPT-4中选择大量的模型。它们的成本不同，其中GPT-4是最昂贵的。值得在[Azure OpenAI playground](https://oai.azure.com/portal/playground?WT.mc_id=academic-105485-koreyst)中研究哪些模型最适合您的需要。

- **多模态**。如果您想要处理输入和输出中的多种类型数据，则可以查看[带有视觉或gpt-4 turbo的gpt-4o](https://learn.microsoft.com/azure/ai-services/openai/concepts/models#gpt-4-and-gpt-4-turbo-models?WT.mc_id=academic-105485-koreyst)等模型- OpenAI模型的最新版本-它们能够将自然语言处理与视觉理解相结合，通过多模态界面实现交互。

选择模型意味着您获得了一些基本功能，但这可能不足够。通常，您拥有特定于公司的数据，需要以某种方式告诉LLM。有几种不同的选择来解决这个问题，在即将到来的章节中会有更多介绍。

### 基础模型与LLMs

术语“基础模型”是由斯坦福研究人员[创造的](https://arxiv.org/abs/2108.07258?WT.mc_id=academic-105485-koreyst)，并定义为遵循某些标准的AI模型，例如：

- **它们是使用无监督学习或自监督学习进行训练的**，这意味着它们是在未标记的多模态数据上进行训练的，并且不需要人类注释或标记数据进行训练过程。
- **它们是非常大的模型**，基于训练在数十亿个参数上的非常深的神经网络。
- **它们通常旨在作为其他模型的“基础”**，这意味着它们可以用作其他模型的起点，可以通过微调来完成。

![基础模型与LLMs](./images/FoundationModel.png?WT.mc_id=academic-105485-koreyst)

图像来源：[基础模型和大型语言模型的基本指南 | Babar M Bhatti | Medium](https://thebabar.medium.com/essential-guide-to-foundation-models-and-large-language-models-27dab58f7404)

为了进一步澄清这种区别，让我们以ChatGPT为例。为了构建ChatGPT的第一个版本，使用了名为GPT-3.5的模型作为基础模型。这意味着OpenAI使用了一些特定于聊天的数据来创建GPT-3.5的调整版本，该版本专门用于在对话场景中表现良好，例如聊天机器人。

![基础模型](./images/Multimodal.png?WT.mc_id=academic-105485-koreyst)

图像来源：[2108.07258.pdf (arxiv.org)](https://arxiv.org/pdf/2108.07258.pdf?WT.mc_id=academic-105485-koreyst)

### 开源与专有模型

分类LLMs的另一种方法是它们是开源还是专有。

开源模型是向公众提供并可被任何人使用的模型。它们通常由创建它们的公司或研究社区提供。这些模型允许进行检查，修改和自定义以用于LLMs的各种用例。但是，它们并不总是针对生产使用进行优化，并且可能不如专有模型效果好。此外，开源模型的资金可能有限，可能不会长期维护或可能不会更新最新的研究。流行的开源模型的示例包括[Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html?WT.mc_id=academic-105485-koreyst)、[Bloom](https://sapling.ai/llm/bloom?WT.mc_id=academic-105485-koreyst)和[LLaMA](https://sapling.ai/llm/llama?WT.mc_id=academic-105485-koreyst)。

专有模型是由公司拥有并且不向公众提供的模型。这些模型通常针对生产使用进行了优化。但是，它们不允许进行检查，修改或自定义以用于不同的用例。此外，它们并不总是免费提供，并且可能需要订阅或付款才能使用。此外，用户无法控制用于训练模型的数据，这意味着他们应该信任模型所有者确保数据隐私和负责任地使用AI。流行的专有模型的示例包括[OpenAI模型](https://platform.openai.com/docs/models/overview?WT.mc_id=academic-105485-koreyst)、[Google Bard](https://sapling.ai/llm/bard?WT.mc_id=academic-105485-koreyst)或[Claude 2](https://www.anthropic.com/index/claude-2?WT.mc_id=academic-105485-koreyst)。

### 嵌入式与图像生成与文本和代码生成

LLMs还可以根据它们生成的输出进行分类。

嵌入式是一组模型，可以将文本转换为数字形式，称为嵌入式，这是输入文本的数字表示。嵌入式使得机器更容易理解单词或句子之间的关系，并且可以作为输入由其他模型（例如分类模型或聚类模型）消耗，这些模型在数字数据上具有更好的性能。嵌入式模型通常用于迁移学习，其中为代理任务构建模型，有大量数据，然后重复使用模型权重（嵌入式）用于其他下游任务。此类别的示例是[OpenAI嵌入式](https://platform.openai.com/docs/models/embeddings?WT.mc_id=academic-105485-koreyst)。

![嵌入式](./images/Embedding.png?WT.mc_id=academic-105485-koreyst)

图像生成模型是生成图像的模型。这些模型通常用于图像编辑，图像合成和图像翻译。图像生成模型通常是在大型图像数据集（例如[LAION-5B](https://laion.ai/blog/laion-5b/?WT.mc_id=academic-105485-koreyst)）上进行训练，并且可以用于生成新图像或使用修复，超分辨率和着色技术编辑现有图像。示例包括[DALL-E-3](https://openai.com/dall-e-3?WT.mc_id=academic-105485-koreyst)和[Stable Diffusion模型](https://github.com/Stability-AI/StableDiffusion?WT.mc_id=academic-105485-koreyst)。

![图像生成](./images/Image.png?WT.mc_id=academic-105485-koreyst)

文本和代码生成模型是生成文本或代码的模型。这些模型通常用于文本摘要，翻译和问答。文本生成模型通常在大型文本数据集（例如[BookCorpus](https://www.cv-foundation.org/openaccess/content_iccv_2015/html/Zhu_Aligning_Books_and_ICCV_2015_paper.html?WT.mc_id=academic-105485-koreyst)）上进行训练，并且可以用于生成新文本或回答问题。代码生成模型，例如[CodeParrot](https://huggingface.co/codeparrot?WT.mc_id=academic-105485-koreyst)，通常在大型代码数据集（例如GitHub）上进行训练，并且可以用于生成新代码或修复现有代码中的错误。

![文本和代码生成](./images/Text.png?WT.mc_id=academic-105485-koreyst)

### 编码器-解码器与仅解码器

要讨论LLMs的不同体系结构类型，请使用类比。

想象一下，您的经理为您分配了一项任务，让您为学生编写一份测验。您有两位同事; 一位负责创建内容，另一位负责审核。

内容创建者就像仅解码器模型一样，他们可以查看主题并查看您已经写过的内容，然后可以编写基于此的课程。他们非常擅长编写引人入胜且信息丰富的内容，但是他们不擅长理解主题和学习目标。解码器模型的一些示例是GPT系列模型，例如GPT-3。

审核员就像编码器模型一样，他们查看编写的课程和答案，注意它们之间的关系并理解上下文，但是他们不擅长生成内容。编码器模型的示例是BERT。

想象一下，我们也可以让某人创建和审核测验，这就是编码器-解码器模型。一些示例是BART和T5。

### 服务与模型

现在，让我们谈谈服务和模型之间的区别。服务是云服务提供商提供的产品，通常是模型，数据和其他组件的组合。模型是服务的核心组件，通常是基础模型，例如LLM。

服务通常针对生产使用进行了优化，并且通常比模型更易于使用，通过图形用户界面。但是，服务并不总是免费提供，并且可能需要订阅或付款才能使用，以换取利用服务所有者的设备和资源，优化费用并轻松扩展。服务的示例是[Azure OpenAI服务](https://learn.microsoft.com/azure/ai-services/openai/overview?WT.mc_id=academic-105485-koreyst)，它提供按使用量付费的费率计划，这意味着用户按使用服务的程度付费。此外，Azure OpenAI服务在模型的功能之上提供企业级安全性和负责任的AI框架。

模型只是神经网络，带有参数，权重和其他内容。允许公司本地运行，但需要购买设备，构建结构以扩展并购买许可证或使用开源模型。像LLaMA这样的模型可供使用，需要计算能力来运行模型。

## 如何在Azure上使用不同的模型进行测试和迭代以了解性能

一旦我们的团队探索了当前的LLMs景观并确定了一些适合其场景的良好候选项，下一步是在其数据和工作负载上测试它们。这是一个迭代过程，通过实验和测量完成。我们在前面的段落中提到的大多数模型（OpenAI模型，Llama2之类的开源模型和Hugging Face转换器）都可以在[Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/what-is-ai-studio?WT.mc_id=academic-105485-koreyst)中的[模型目录](https://learn.microsoft.com/azure/ai-studio/how-to/model-catalog-overview?WT.mc_id=academic-105485-koreyst)中找到。

[Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/what-is-ai-studio?WT.mc_id=academic-105485-koreyst)是一个云平台，旨在为开发人员构建生成式AI应用程序并将整个开发生命周期（从实验到评估）管理在一个单一的中心点，并将所有Azure AI服务组合成一个便捷的GUI。 Azure AI Studio中的模型目录使用户能够：

- 在目录中查找感兴趣的基础模型-专有或开源，按任务，许可证或名称进行过滤。为了提高可搜索性，模型被组织成集合，例如Azure OpenAI集合，Hugging Face集合等。

![模型目录](./images/AzureAIStudioModelCatalog.png?WT.mc_id=academic-105485-koreyst)

- 查看模型卡片，包括预期使用和训练数据的详细说明，代码示例以及内部评估库中的评估结果。

![模型卡片](./images/ModelCard.png?WT.mc_id=academic-105485-koreyst)

- 比较行业中
根据用户的期望，答案将会是什么。在这种情况下，如果提示只包含一个示例，则称为“一次性”学习，“少量学习”如果包括多个示例。带有上下文的提示工程是启动的最具成本效益的方法。###检索增强生成（RAG）LLM存在限制，即它们只能使用在其培训过程中使用过的数据来生成答案。这意味着它们对于培训过程之后发生的事实一无所知，并且无法访问非公开信息（例如公司数据）。这可以通过RAG克服，一种技术，它将外部数据以文档块的形式与提示一起增强，考虑提示长度限制。这得到了矢量数据库工具的支持（例如[Azure Vector Search]（https://learn.microsoft.com/azure/search/vector-search-overview?WT.mc_id=academic-105485-koreyst）），该工具从各种预定义数据源中检索有用的块并将它们添加到提示上下文中。当企业没有足够的数据，足够的时间或资源来微调LLM，但仍希望在特定工作负载上提高性能并减少虚构（即现实或有害内容的神秘化）风险时，这种技术非常有用。###微调模型微调是一种利用转移学习来“适应”模型到下游任务或解决特定问题的过程。与少量学习和RAG不同，它会生成一个新模型，具有更新的权重和偏差。它需要一组训练示例，包括单个输入（提示）及其相关输出（完成）。如果：-**使用微调模型**。企业希望使用微调的性能较低的模型（如嵌入模型）而不是高性能模型，从而得到更具成本效益和快速的解决方案。-**考虑延迟**。延迟对于特定的用例很重要，因此不可能使用非常长的提示或应从模型中学习的示例数不符合提示长度限制。-**保持最新状态**。企业拥有大量高质量数据和基本事实标签，并具备维护此数据随时间保持最新所需的资源。###训练模型从头开始训练LLM无疑是采用的最困难和最复杂的方法，需要大量数据，熟练的资源和适当的计算能力。仅在企业具有特定领域用例和大量领域中心数据的情况下才应考虑此选项。##知识检查如何改善LLM完成结果的好方法是什么？1.带有上下文的提示工程1.RAG1.微调模型A：3，如果您有时间和资源以及高质量数据，则微调是保持最新状态的更好选择。但是，如果您正在寻求改进并且缺乏时间，则首先考虑RAG是值得的。##🚀挑战了解如何为您的业务[使用RAG]（https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview?WT.mc_id=academic-105485-koreyst）。##干得好，继续学习完成此课程后，请查看我们的[生成AI学习收藏夹]（https://aka.ms/genai-collection?WT.mc_id=academic-105485-koreyst）以继续提高您的生成AI知识水平！转到第3课，我们将看看如何[负责任地使用生成AI构建]（../03-using-generative-ai-responsibly/README.md?WT.mc_id=academic-105485-koreyst）！


免责声明：本翻译是由人工智能模型翻译的，可能不完美。请仔细查看输出并进行必要的更正。