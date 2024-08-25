
---
categories: 人工智能
cover: https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*Nv-jqOQi2KmHhcvxTe1CQA.jpeg
date: '2024-08-15 22:11:09'
tags:
  - AI图像生成
  - Grok平台
  - Flux模型
title: Flux 现已集成到 xAI 的 Grok2 中

---




这是官方消息。来自 Blackforest Labs 的最新且最强大的 AI 图像模型 [Flux](https://jimclydemonge.medium.com/flux-1-is-a-mind-blowing-open-weights-ai-image-generator-with-12b-parameters-5a138146bb51) 已通过 [Grok](https://generativeai.pub/grok-1-is-now-available-to-x-premium-subscribers-5756585612fe) 集成到埃隆·马斯克的 X 平台中。此次集成是最近推出的 [Grok-2 和 Grok-2-mini 模型](https://x.ai/blog/grok-2) 的一部分，这些模型在聊天、编码和推理方面具有尖端能力。

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*WhFhns6QQ0SRkKjDzY6kGQ.png)

## 什么是 Flux？

Flux.1 是一系列最新的文本到图像模型（SOTA），在图像细节、提示准确性、风格多样性和场景复杂性方面为文本到图像生成设定了新标准。

它有三个变体：

* **Flux.1 Pro**：该模型在图像生成方面提供了更高水平的性能，特别是在提示遵循、视觉质量、图像细节和输出多样性方面表现出色。
* **Flux.1 Dev**：这是一个为非商业用途量身定制的指导蒸馏模型，源自 Flux.1 Pro，提供可比的质量和提示准确性，同时比同类模型更高效。
* **Flux.1 Schnell**：该系列中速度最快的模型，专为本地开发和个人使用而设计，采用 Apache 2.0 许可证。

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*6gaDfjgc3yuePMZ-.png)

所有 Flux.1 模型都结合了多模态和 [并行](https://arxiv.org/abs/2302.05442) [扩散变换器](https://arxiv.org/abs/2212.09748) 块，具有 120 亿个参数。这些模型通过利用 [流匹配](https://arxiv.org/abs/2210.02747) 超越了以前的扩散模型，流匹配是一种简单的生成模型训练方法，结合了扩散。

此外，这些模型通过使用 [旋转位置嵌入](https://arxiv.org/abs/2104.09864) 和 [并行注意力层](https://arxiv.org/abs/2302.05442) 实现了更好的性能和硬件效率。

虽然没有明确说明在 Grok AI 中使用的是哪个特定的 Flux 图像模型，但图像的质量表明它很可能是 Dev 或 Pro 模型。图像的细节水平和丰富性令人瞩目，这使我倾向于 Pro 模型。

## 如何在Grok上生成图像？

在Grok上生成图像非常简单，但您需要是X平台的Premium或Premium+用户。登录后，只需导航到左侧边栏并点击Grok按钮。从那里，您可以描述您想要创建的图像。

这是一个例子：

> 提示：制作一张吸引人的网红在TED演讲的图像

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*kRdAknqdf5lRZ3ymNWZFNw.png)

为了让您了解Grok与Midjourney的对比，这里是使用相同提示生成的图像的并排比较：

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*5hZCb9jbQKlS_nNpRf47Fg.jpeg)

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*mNe13dVLcYZmGzZ6)

您更喜欢哪一个？

就我个人而言，我觉得Grok生成的图像更具吸引力。虽然Midjourney的图像有更多的纹理和更细致的细节，但它也有一种令人不安的谷效应，让人感觉稍微有些人工。另一方面，Grok的图像看起来更自然，色调更柔和，饱和度更低。

我还将相同的提示输入到ChatGPT（使用Dall-E 3），这是我得到的结果：

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*WLw0tEctdUcfI-4SmU2iJA.png)

结果还不错，但与Midjourney或Grok的质量相比，还是有些差距。

这是另一个例子：

> 提示：带有VSCO滤镜的宝丽来照片，1990年，迷人的女性，夜晚，闪光照片，金发，可爱，年轻的面孔，美丽的阴影，热带植物，城市服装，公寓内部，单反相机，手持写有“这张照片是为Generative AI Publication使用Grok 2 Mini创建的”笔记本上的标志。

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*5qpwnsrMx8HtvF4SLHuN_g.jpeg)

这真是令人印象深刻。图像不仅看起来逼真，而且完美地捕捉了提示中描述的特定风格和氛围。文本渲染也非常好，尽管有一个小遗漏（文本中缺少“was”）。

## 高度宽松的图像模型

Grok的图像生成功能没有限制，允许用户创建几乎任何类型的图像。看看一些X用户生成的唐纳德·特朗普和卡马拉·哈里斯的图像：

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*wgLmWkmtnV2YeMmf)

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*34GbgTOzQBDrt5aM)

一些用户指出，尽管Grok声称有一些限制——例如避免色情或过于暴力的内容——但这些规则似乎执行得并不一致。这种宽松与其他主要的AI图像生成器形成鲜明对比，后者通常会拒绝涉及真实人物的提示或自动在其图像上添加识别水印。

由于对生成图像类型没有限制，Grok很容易被用作在X和其他平台上创建虚假信息的工具。

## 费用是多少？

访问Grok的图像生成功能仅限于高级用户，订阅费用为每月$8。

这个价格相对具有竞争力，尤其是与其他AI工具相比。例如，ChatGPT的GPT-4模型每月收费$20，而Midjourney每月收费$10。

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*guL9R6sgzerG_a8IIMj32A.jpeg)

当然，这并不意味着你就一定能物有所值。ChatGPT的GPT-4o在语言模型质量上似乎远远领先于Grok，而Midjourney则提供了更广泛的图像自定义选项。

权衡你所获得的与在功能和灵活性方面可能牺牲的东西。

## API 访问

对于开发者来说，还有更多值得期待的内容。X.ai 计划在本月晚些时候通过企业 API 提供 Grok-2 和 Grok-2-mini 模型。

> 我们还将在本月晚些时候通过我们的新企业 API 平台向开发者发布 Grok-2 和 Grok-2 mini。我们即将推出的 API 基于一个全新的定制技术栈，允许在多个区域进行推理部署，以实现全球范围内的低延迟访问。

## 最后的想法

Grok已经存在一段时间了，但它一直未能跟上像ChatGPT和Claude AI这样的竞争对手——直到现在。Flux的整合使这个平台焕发了新生，我发现这个聊天机器人再次变得有趣。

随着Flux将Stable Diffusion推向了聚光灯之外，看看Stability AI将如何回应将会很有趣。他们会很快发布改进版的SD3模型吗？来吧，Stability AI，别轻易放弃。

此外，Blackforest Labs在其网站上暗示了进一步的发展，包括一个新的文本转视频模型。如果这个也被整合到Grok中，它可能对OpenAI和Anthropic这样的巨头构成严重威胁。

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*ieXtq8EMvoKs9t25.png)

此故事发布在[Generative AI](https://generativeai.pub/)。在[LinkedIn](https://www.linkedin.com/company/generative-ai-publication)上与我们联系，并关注[Zeniteq](https://www.zeniteq.com/)，以获取最新的AI故事。

订阅我们的[新闻通讯](https://www.generativeaipub.com/)和[YouTube](https://www.youtube.com/@generativeaipub)频道，以获取生成AI的最新新闻和更新。让我们一起塑造AI的未来！

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*HA-KdrCLBdbzMNoa.png)
