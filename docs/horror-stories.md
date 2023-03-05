# 开发者恐怖故事竞赛| Harness

> 原文：<https://www.harness.io/blog/horror-stories>

迁移噩梦、血腥的错误、可怕的失败——太多让我们咬牙切齿的事情。

这是一年中最恐怖的时刻，我们对您通过我们的开发者恐怖故事竞赛提交的恐怖故事感到兴奋。毫无疑问，我们很难选出最可怕的女巫。迁移噩梦、血腥的错误、可怕的失败——太多让我们咬牙切齿的事情。

## 故事#1:被诅咒的电脑

因此，这是一个售前项目，合同的签署取决于工作演示。我召集了一个开发团队，我们建立了一个概念验证。这是一个运行在桌面上的简单的网络应用程序。为什么选择桌面？因为现在还是 2012 年，云不是东西。我们基本上是将台式电脑重新用于这些简单的用例。在概念验证完全完成后，我们的团队前往客户的办公室演示应用程序。我们总共有 4 个场景要展示和讲述。直到我们在演示中超过 50%的时候，一切看起来都很正常。似乎什么都不管用。客户表示理解，并愿意在第二天观看演示的其余部分，进展顺利。

那么，为什么会失败呢？想象一下，一个新员工走到一台台式电脑前，因为看到桌子已经两天没人用了，就关掉电脑省电。谢谢兄弟！

## 故事#2:令人毛骨悚然的迁移噩梦

当时我们正在开发我们的绿色产品——我猜我们会归类为可再生能源技术项目——我们是一家大型 AWS 商店。正如你所想象的，所有那些构成服务的微服务都由与 AWS 服务的集成提供支持，如 S3、RDS、SQS、Lambda 等等。这些都是亚马逊的服务，我们依靠这些服务来支持我们对这种可再生产品的应用。当时，我们决定迁移到 Azure。

我们对它了解不多，也没有太多相关的专业知识。我们的许多队友以前来自 AWS 商店，所以这对我们来说确实是一个未知的领域。我们让我们的一个团队负责并计算出，“好吧，从 AWS 迁移到 Azure 需要什么？”

当时，Azure 仍处于上升期。在功能对等性和满足我们的监管需求所需的服务和能力方面，它仍然远远落后于 AWS，因为这是可再生能源。我们必须确保数据是安全的，交易是实时发生的，时间序列指标总是以适当的方式传输。当我们对比 Azure 和 AWS 时，我们会考虑这些因素。

最终，我们决定了价格。Azure 更便宜，他们给了我们更多的东西，比如微软团队——整个 office 包——还有这个主要的 Azure 信用。因此，我们在没有完全理解部署应用程序并将其与服务集成意味着什么的情况下就开始了迁移。我们完成了工作，许多团队能够采用 Azure 并拼凑一些解决方案来集成他们的服务。然而，这不是一对一的。作为一家企业，我们在想，“嗯，我们需要尽快从 AWS 转移到 Azure。”我们的客户正在等待这项服务，以便他们可以根据自己的需要使用它。我们坐在这里，慢慢地移动它。我们正在对每一项微服务进行“试火”。我们正试图找出什么不起作用。应用程序关闭是因为我们使用的 Azure 服务没有按照我们期望的方式返回数据，或者因为网络，我们无法与资源对话。

这是一场灾难。我们完成了所有这些工作，领导层发生了变化，我们已经完成了迁移的 25%。一年多过去了，我们的领导层发生了变化。发生的事情是，他们就像，“哦，我的上帝，为什么这需要这么长时间？我们真的要为了转向不同的云提供商而节省一些钱吗？我不这么认为。”

他们将所有迁移的应用程序移回 AWS。对于我们这些已经开始停止一些服务的人来说，我们必须重新整合 AWS。所以这又增加了 6 个月的工作量。人们非常愤怒，因为他们花了太多时间来制定迁移策略。队友们已经给了我们一些框架，用于迁移我们其余的服务。这只是归结到-我们认为这是基于价格，但现实是我们从来没有需要经历这种痛苦。我们最终回到了 AWS。

我还记得很多球队超级不爽。在他们中的一些人辞职去湾区创业后，他们就像这样，“我们已经受够了这种大公司的心态。如果我们需要 Azure 中的某些服务来签署协议，为什么我们必须迁移？我们应该采用多云策略，而不是迁移。

我在这里学到的经验是，当你做出这样的重大决定时，你应该以一种不依赖于你的云提供商的方式来设计你的应用。你应该有一个通用的合同，这样你就可以与这些云提供商的服务进行沟通，因为你永远不知道。明天，你可能需要在不同的云提供商那里寻找不同的客户群。您需要确保您的应用程序在这方面具有弹性和灵活性。

但在那之后的几个月里，所有的工作都很可怕。这就像你在跑马拉松，你是第一名，但你在最后一英里受伤了。这就是我们的感觉。太可怕了。太可怕了。但是你知道，从那可以学到很多东西。展望未来，请确保您有一条坚实的道路，确保您的应用程序不依赖于特定的云提供商，设计您的应用程序以拥有一个允许您与其他东西集成的平台层。这些都是我们从这个时代学到的东西。

## 故事#3:可怕的失败

我们与 Pivotal 签订了一份大合同，当时 Pivotal 是戴尔旗下的一家公司。他们正在推动 pair programming，即 12 因素应用程序，能够构建一个应用程序并快速将其部署到托管的 pass 层，因此您不必担心 AWS，也不必担心区域。Cloud Foundry 是在此之上的一个很好的层，可以消除这种复杂性。

我们大量使用 Cloud Foundry 来部署许多面向业务的应用程序和面向消费者的应用程序。Cloud Foundry 有其优势，但当我们需要做更复杂的事情时，如金丝雀部署、蓝绿色部署，然后能够在本地环境或离线的本地环境中运行这些应用程序，这真的不容易。

我们需要将这些应用容器化，因为 Cloud Foundry 的内部安装没有得到我们许多客户的认可。他们受到严格监管。他们批准了 Docker，还批准了 Kubernetes on-premise。因此，我们不得不经历这种迁移，我们将移植我们所有的 Cloud Foundry 应用程序，这些应用程序当时还不是 Dockerized 应用程序。它们是 jar、war 和 zip 文件，部署到一个 prod 空间，本质上是供人们使用的。我们使用了所有这些插件，比如自动缩放插件。我们总是不得不管理构建包，找出哪些是我们需要使用的，哪些是我们不兼容的。

在 Docker 的努力下，它要求我们确保我们拥有所有的依赖项，所有的东西都准备好了，这样当这个容器旋转起来时，它就可以实际运行了，除此之外，它还可以与其他服务进行通信。除此之外，我们还有另一个复杂性，那就是学习 Kubernetes。我们有一个执行 CI/CD 的内部工具，但它部署在一个中间层容器化集群上。那不是库伯内特。它有自己的部署方式。我们被困在这个地方，我们必须学习 Kubernetes，然后想出一个迁移策略，将所有这些面向业务的应用程序迁移到 Kubernetes 上，并将其容器化。

挑战在于我们有 6 个月的期限。我们想出了一个迁移工具来迁移这些应用程序。事实是，当我们试图这样做时，我们也走了完全的核心开发者路线，那就是，“哦，我们必须在我们自己的本地集群上建立 Kubernetes，我们不想消耗 EKS 或任何其他服务提供商的资源。”最重要的是，我们必须管理 RBAC，并拿出迁移工具来查看，“好吧，这些 PCF 清单需要转换成 Kubernetes 风格的清单，我们甚至不知道所有的映射是什么。”所以我们不得不提出混合映射模型。

我们试图对开发人员隐瞒 Kubernetes，这样他们就不会费力去理解这些 yamls 是由什么组成的，只是他们给了我们一个应用程序，我们神奇地将它从 PCF 转换成 Kubernetes。

我们尝试了前三个应用程序，但都不起作用。我们的地图是错误的。容器未能变得健康。人们不明白什么是服务。人们不知道吊舱的概念。他们不熟悉 Kubernetes 如何编排和调度这些容器，他们没有有状态应用程序的概念，或者如果有一个服务需要 DB，您希望它有一个持久卷。那里也没有。

当我们迁移过来的时候，我们错过了很多东西。结果，我们有 6 个月的时间表，我们就是达不到。我们实际上失败了。经历了又一次失败的迁移后，这一次成了许多人的最后一根稻草。我们认为我们已经从之前的失败迁移中吸取了教训。我们有一个迁移策略，我们有映射，它是自动化的，因此用户不必费力地完成它或为它做任何繁重的工作。但是我们只是达不到要求，因为 a)我们自己对 Kubernetes 的了解是不正确的，b)当我们做建模时，我们从来没有考虑到所有这些极限情况。我们发现，并不是所有的应用程序都以相同的方式制作，也不是所有的应用程序都以相同的方式部署。这些 PCF 应用程序被强制安装到我们设计的这个模板中。

我们最终把这些工作都废弃了。情况变得如此糟糕，以至于人们会说，“忘了它吧，我们会用 Cloud Foundry 挺过去的。事实上，如果我们真的想的话，我们可以去开源 Cloud Foundry 并管理我们自己的所有节点和整个 Cloud Foundry 安装，但我们不会在 Kubernetes 上投入更多的精力。那是不可能的。”

这导致人们变得非常不安。那个项目之后很多队友都离开了，因为那是他们最后的救命稻草。这是另一个可怕的故事:你必须确保你有这些计划。否则你会陷入混乱，人们不高兴，他们做了所有这些工作，试图把东西带过来，但这不起作用。您浪费了您团队的时间，也浪费了您业务的时间，而您使用该应用程序的客户会说，“见鬼，你们把它拆了，这样就可以发布新版本了，但它却不在那里。你必须重新打开旧的应用程序。”太臭了。这让企业损失了很多钱，而且很可能会让人们丢掉工作。如果你做得不对，这是一个危险的游戏。

## 故事#4:不情愿的疯虫

几年前，我受雇定制一个财务系统。我做的第一个测试在我面前爆炸了。原来我的前任会在没有数据的情况下测试系统，如果可以运行，就把它转移到生产环境中。程序员的姓是“Bugg”

-

你有它，食尸鬼和女孩，可怕的故事，以填补你的坟墓。明年见——在那之前，慢慢来。