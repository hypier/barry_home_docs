
---
categories: 人工智能
cover: https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*LWorbwqFjVku5YSmQArEgQ.png
date: '2024-07-18 01:15:38'
tags:
  - AI代理
  - 多模态模型
  - 网页浏览
title: Agentic AI：创建可以浏览互联网的 AI 代理

---


# 自主性AI打造能畅游互联网的AI代理

## WebVoyager 是一款具备视觉能力的网页浏览代理，能够自主导航互联网。它通过解读每个状态下的带注释浏览器截图，来决定下一步操作。

# 引言

考虑到OpenAI，无论是`GPT-4o`还是`GPT-4 Turbo`模型，都具备视觉处理能力。因此，这些模型能够接收图像并根据图像内容回答问题。

以往的语言模型（LMs）只能处理文本输入，即单一输入模式。

但除了让基础模型（FM）接收图像并进行描述外，代理应用或代理AI还可以实时标注网页，并通过浏览网页来找到答案。

# WebVoyager

WebVoyager 是一款基于最新研究 [*WebVoyager*](https://arxiv.org/pdf/2401.13919) 的 [AI 代理应用](https://github.com/langchain-ai/langgraph/blob/main/examples/web-navigation/web_voyager.ipynb)，该研究名为《利用大型多模态模型构建端到端网页代理》。

WebVoyager 是一个具备视觉能力的网页浏览代理，能够控制鼠标和键盘。它通过分析每一步的浏览器截图注释来确定下一步行动。

该代理采用基本的推理与行动（ReAct）循环架构，其独特功能包括：

* 使用类似 Set-of-Marks 的图像注释作为界面操作提示。
* 在浏览器环境中应用，利用工具控制鼠标和键盘。

# 现实场景中的自主应用

AI代理，亦称为代理应用，在形式上曾局限于文本。因此，该代理仅能访问多种工具，例如数学库、基于文本的网络搜索、一个或多个API调用等。

因此，当前代理虽能访问网络工具，但通常仅处理单一输入形式（文本），并且仅在简化的网络模拟器或静态网页快照中进行评估。

WebVoyager是一款创新的大型多模态模型（LMM）驱动的网络代理，旨在通过与真实世界网站互动，完成用户指令的端到端执行。

例如，WebVoyager被问及：`能否查看谷歌地图，确定我从旧金山市中心出发，在7点前到达SFO的最佳出发时间？`

以下是Python代码示例及带注释的截图…

```python
res = await call_agent(
    "Could you check google maps to see when i should leave to get to SFO by 7 o'clock? starting from SF downtown.",
    page,
)
print(f"Final response: {res}")
```
![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*fwqC3Ksduw2zZ-5oqr9XCg.png)

# 利用多模态理解能力

近期研究探讨了构建基于文本的网页浏览环境以及如何指导大型语言模型代理进行网页导航。

这一新进展着重于构建多模态网页代理，通过截图利用浏览器渲染的环境，从而模拟人类的网页浏览行为。

**WebVoyager** 是一个多模态网页AI代理，旨在自主完成从始至终的在线网页任务，全程无需任何中间人工干预。

**WebVoyager** 通过从截图和交互式网页元素中的文本内容进行观察，处理用户查询，并构思采取何种行动。

行动可能包括点击、输入、滚动等，并在网站上执行该行动。

> 以下是根据网页导航中的标注截图，展示代理遵循的事件序列。

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*_QE6_y_Fbsa4LqeA6rw54g.png)

# 观察空间

与人类浏览网页类似，该代理主要通过网页的视觉信息（**截图**）作为输入。

这种方法避免了处理HTML DOM树或可访问性树的复杂性，这些处理可能会产生过于冗长的文本，并阻碍代理的决策过程。

与苹果在Ferret-UI中采用的方法非常相似，研究人员在**网站**的**交互元素**上覆盖边界框，以更好地指导代理的动作预测。

这种方法不需要对象检测模块，而是使用GPT-4V-ACT5，一个JavaScript工具，根据网页元素类型提取交互元素，并在相应区域上覆盖带有数字标签的边界框。

GPT-4V-ACT5效率高，因为它基于规则，不依赖任何对象检测模型。

# 动作空间

WebVoyager 的动作空间设计旨在紧密模拟人类的网页浏览行为。通过实现最常用的鼠标和键盘操作，使代理能够有效导航。

利用截图中的数字标签，代理可以响应简洁的动作格式。这种方法精确识别交互元素并执行相应操作。

**主要动作包括：**

1. **点击**：点击网页元素，如链接或按钮。
2. **输入**：选择文本框，清除现有内容并输入新内容。
3. **滚动**：垂直移动网页。
4. **等待**：暂停以允许网页加载。
5. **返回**：返回上一页。
6. **跳转至搜索引擎**：在网站上找不到答案时重定向至搜索引擎。
7. **回答**：通过提供符合任务要求的答案来结束迭代。

这些动作使代理能够高效地与网页交互，模拟类似人类的浏览体验。

# 以下是完整在线网页浏览轨迹的截图

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/1*8AYbG36naO8nsSXx0BmpJA.png)

## 任务：

“在苹果官网搜索适用于iPad的智能保护盖Smart Folio，并查看在邮编90038附近的最近自提点可用性。”

## 流程：

**初步搜索：** 代理访问苹果官网并使用搜索功能查找“iPad智能保护盖”。

**产品选择：** 代理点击相应的搜索结果以打开产品页面。

**检查可用性：** 代理输入邮政编码“90038”以检查最近的取货可用性。

**结果：** 代理确认“Apple Tower Theatre”为最近的取货地点。

## 洞察：

**直接交互：** 与网站的直接交互对于完成任务是必要的。

**多模态必要性：** 文本和视觉输入对于代理作为通用网络代理有效运作至关重要。

**交互元素的挑战：** 具有更多交互元素的网站对代理来说是一个更大的挑战，因为导航和与各种组件交互的复杂性增加。

**多模态必要性：** 文本和视觉输入对于代理作为通用网络代理有效运作至关重要。

**难处理元素的挑战：** 具有更多交互元素的网站对代理来说是一个更大的挑战，因为导航和与各种组件交互的复杂性增加。

WebVoyager处理这项任务的能力突显了其在自主执行复杂网络导航和交互任务方面的熟练程度，利用视觉和文本信息实现准确和高效的结果。

# 最终

WebVoyager 是一款创新的网络代理，由大型多模态模型（LMMs）驱动，旨在通过与网站互动来完成端到端的现实世界网络任务。

评估显示，WebVoyager 通过有效利用视觉和文本信号，超越了多个基准。

这项研究展示了利用先进 LMM 能力构建智能网络代理的潜力。WebVoyager 旨在为未来专注于开发更全能和高效网络助手研究提供坚实基础。

WebVoyager 系统提示。我们指导代理进行网络导航，以及特定的浏览操作和操作格式。为了提高效率和准确性，我们可以在提示中加入额外的通用指南。这些指南应具有普遍性，不针对特定网站，以确保通用性。

```python
想象你是像人类一样浏览网页的机器人。现在你需要完成一项任务。在每次迭代中，你将收到一个包含网页截图和一些文本的观察结果。截图中每个网页元素的左上角都会放置一个数字标签。仔细分析视觉信息，识别需要交互的网页元素对应的数字标签，然后遵循指南并选择以下操作之一：
1. 点击网页元素。
2. 删除文本框中的现有内容，然后输入内容。
3. 向上或向下滚动。
...
相应的，操作应严格遵循以下格式：
- 点击 [数字标签]
- 输入 [数字标签]; [内容]
- 滚动 [数字标签或窗口]; [向上或向下]
- 等待
- 返回
- 谷歌搜索
- 回答; [内容]
关键指南你必须遵循：
* 操作指南 *
1) 每次迭代只执行一个操作。
...
* 网页浏览指南 *
1) 不要与网页中出现的无用网页元素（如登录、注册、捐赠）进行交互。
...
你的回复应严格遵循以下格式：
思考：{你的简短思考（简要总结有助于回答的信息）} 操作：{你选择的操作格式}
然后用户将提供：
观察：{用户提供的带标签截图}
```
***⭐️ 在 [LinkedIn](https://www.linkedin.com/in/cobusgreyling/) 上关注我，获取大型语言模型更新 ⭐️***

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*4fhM_IeU0f1_HTOF.png)

*我目前是 [Kore AI](https://blog.kore.ai/cobus-greyling) 的 [首席传道者](https://www.linkedin.com/in/cobusgreyling)。我探索并撰写关于 AI 与语言交叉领域的所有事物；从 LLMs、聊天机器人、语音机器人、开发框架、以数据为中心的潜在空间等。*

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*VsJ7ciiPu_1PCKbr.png)

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*D2Tlw5Y5diPHEcJD.jpeg)

![](https://cdn-images-1.readmedium.com/v2/resize:fit:800/0*3a27sfPh-8JrafRt.png)
