# 使用功能标志|线束时的 5 个常见挑战

> 原文：<https://www.harness.io/blog/feature-flags-challenges>

我们已经谈了好的方面，现在让我们谈谈坏的方面。尽管如此，还是有好消息:当谈到特性标志时，即使是“坏的”也很容易解决。

使用特性标志有很多好处。我们已经在[中讨论了很多，软件交付中特性标志的好处](https://harness.io/blog/benefits-of-feature-flags/)和 [5 个你可能没有想到的特性标志用例](https://harness.io/blog/feature-flag-use-cases/)。然而，就像你工作方式的任何改变一样，你可能会发现一些你没有预先计划的关于特性标志的挑战。

特性标志最终很容易有效地管理，但是它们确实需要一些新的过程和对话，值得提前了解。我们将在这里看看五个非常常见的问题，我们建议你在采用功能标志时提前考虑——以及如何解决它们。

## 挑战#1:随着时间的推移，标志越来越多。

“我们不知道该去掉哪一个，也没人知道这个问题！”

随着时间的推移，我们正在努力使 Harness 功能标志更有能力解决这个问题，现在有很多简单的方法可供团队改进。

实际上有两个问题需要跟踪:

1.  谁拥有一面旗帜？
2.  旗帜还在使用吗？

您可以使用标志名称和描述模板、电子表格、wiki 页面或任何其他跟踪文档来完成此操作。确保无论最终负责方是谁——无论是项目管理、工程、运营还是项目管理——都定期检查他们的标志并相应地更新状态。

## 挑战#2:我们从来没有从代码中移除标志。

不管旗帜归谁所有，工程部门最终都必须移除它。

当思考陈旧旗帜永远挥之不去的问题时，两个重要的问题是:

1.  什么时候可以移除旗帜？
2.  工程实际上应该什么时候移除它？

如果您负责维护标志的状态(如上所述)，那么您只需让工程部门知道标志已经达到了它的目的。有时，这也涉及到获取他们的输入——如果没有一个标志来取消这个特性，他们会感到舒服吗？

一旦标志状态被传达给工程部门(或与他们一起决定)，团队接下来将考虑在哪里找到时间来反对。是技术债、bug、预定的功能工作，还是别的什么？

答案可以是这些事情中的任何一个，只要你的团队是明确的。一般来说，越早把一面陈旧的旗帜拿出来越好——因为这些东西有动量。为每个 sprint 留出一个故事来清理标志，或者每个季度一个 sprint，或者其他一些明显被封锁的时间，承认标志是你的过程的重要部分，清理标志是使用标志的重要部分。

## 挑战# 3——旗帜名称非常注重工程设计

有时，当工程师创建标志时，像“OLD_SWITCH_ULNG”这样的名称对他们来说非常有意义。但是，当 PM 或其他人开始使用该标志进行外部访问时，它们就丢失了。我们想要“OLD_SWITCH_ULNG”还是“OLD _ SWITCH _ ULNG _ BE”——或者两者都要？

项目经理可以与工程师合作，预先决定命名模板，以帮助这个过程。一些好的基本规则是:

*   标志名应该描述标志的变化。
*   应该始终有一个有用的、描述客户影响的标志描述。
*   在标志名称中描述状态(即，当状态改变时，将“生产就绪”或其他内容附加到标志)。

通过一些简单的协议，可以很容易地避免这种限制整个组织使用标志的常见命名陷阱。

## 挑战#4 -谁为顾客打开旗帜？

让我为你描述一个在我们的旗帜之旅中从未发生过的场景:

*   一位客户经理很高兴能向客户提供测试版功能，客户也同意了。
*   客户经理要求销售工程师打开该功能。
*   销售工程师要求支持代表打开该功能。
*   支持代表要求项目经理打开该功能。
*   PM 不知道使用哪个标志，所以他中断工程并要求他们打开该功能。

使用 flags 的一大优势是增强了组织中其他人的能力，但是在这种情况下，您将会分散几乎所有可能的人的注意力，而这种改变最终只需要几秒钟。

为了避免这种情况，你的主要利益相关者——支持、客户团队、eng 和 PMs——都应该就公司中谁将是为客户打开和关闭事物的主要资源达成一致。在 Harness，我们主要依靠客户团队，需要时由项目经理提供支持。有时，对于由项目经理更密切领导的测试版，我们会稍微颠倒一下这个过程。

应该注意的是，有些标志实际上不会以可见或直接的方式影响客户。严格意义上的后端更改，比如 API 重构，不需要针对每个客户进行，只需要在全球范围内进行可靠性测试。对于这样的标志，您可能有某种替代的过程，其中工程端到端地拥有标志。

## 挑战# 5——在使用功能标志时，我们如何保证产品环境的安全？

这个问题经常在过程的后期出现。产品和工程团队开始使用标志并向前移动，最后，一名安全人员查看一下。他们看到*更多的人现在有可能在生产中立即做出面向客户的改变，而不需要部署或回滚的沉重技术负担。如果他们以前没有使用过特征标志，他们可能会感到惊慌。*

幸运的是，Harness Feature Flags 有一个全面的 RBAC 模型，很容易控制谁应该访问哪些环境。这意味着你需要在内部解决的唯一事情是**谁控制访问**和**什么团队应该有访问**。

一种常见的情况是，所有工程人员都可以无限制地访问 prod，但是在 prod 中，只有工程人员的一个子集(如经理或运营人员)可以访问。相反，Prod 标志主要由项目经理和客户团队控制，由项目管理或运营部门监督访问配置。

有这样一个严格的大纲，有明确的人负责加入和审计用户访问和配置，这对于在使用特性标志时保持一切合规和安全是至关重要的。

## 结论

不管这些答案有多长，你可能会注意到大部分都是一个答案:沟通！

标志代表一种新的工作方式，这意味着改变您的团队以前做事的方式。不过，这些变化在很大程度上不是技术性的，而是归结到谁在何时做什么。

有了良好的内部沟通和规划，几乎所有第一次使用特性标志所带来的新挑战都可以被轻松克服。

想了解更多关于特性标志的信息吗？这里有一篇关于迁移特性标志工具时的最佳实践的文章。并且，请留意我们的[资源](https://harness.io/learn/resource-center/#assets)页面——我们将很快推出一个免费的、无闸门的功能标志电子书，这样你就可以对讨厌的功能标志挑战说再见了！