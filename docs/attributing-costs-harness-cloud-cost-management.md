# 使用利用云成本管理|利用来确定成本

> 原文：<https://www.harness.io/blog/attributing-costs-harness-cloud-cost-management>

云成本涉及的人/团队相当多。从开发人员和预算负责人到财务人员，每个人都需要能够看到浪费的地方。归因成本和优化对成功至关重要。让我们看看如何利用线束 CCM 实现这一点！

从根本上说，管理云成本是一个简单的三步流程:确定成本、优化和治理。云使团队能够快速移动，并利用最新的技术和服务以前所未有的速度进行创新。开发人员喜欢优化，灌输以成本为中心的思维模式，将成本优化作为另一个边界条件，将有助于财务和工程团队高效运营。为了进行优化，开发人员、财务团队、云预算所有者和利益相关者需要了解来自各种公共云的成本。

开发人员希望看到他们负责的一组精确的微服务的成本。此外，他们希望看到潜在浪费的确切区域，以及可靠的建议。然后，云预算所有者希望看到他们负责的资源成本，以及治理护栏。另一方面，财务团队希望对整体数据进行分割，以便对预订做出明智的决策，并对未来成本进行准确的规划和建模。但是怎么做呢？

## CCM 视角

利用 CCM 视角可以让您以对您的业务需求更有意义的方式对资源进行分组。它提供了您的多云成本数据的统一视图，具有管理治理和提供上下文优化机会的灵活性。

利用自定义云成本视角，用户只需添加规则即可查看自己拥有或管理的数据。在上面的例子中，我们有一个多云场景，其中特定用户拥有跨云的资源。通过向 perspective builder 添加三个简单的规则，我们可以快速预览跨云产品的成本。用户还可以更改默认的日期范围、分组依据和可视化选项。

透视图有助于优化、治理和可视化上下文中的数据。一旦我们使用规则定义了透视图的范围，就可以设置报告来接收按照计划发送的电子邮件。预算也可以在透视图的范围内设置。这使用户能够设置粒度警报，以便在达到特定成本阈值时通知目标用户组。这些观点甚至超越了这一点，通过提供可操作的建议来降低成本并满足现有的治理护栏。

透视图还提供了对使用指标的 [Kubernetes](https://aws.amazon.com/eks/) 成本支出的深入了解，例如*闲置成本*——这是一个基于请求和实际利用率的浪费支出指标，以及*未分配成本*——这是一个对正在旋转节点但未被请求的已支付成本的度量。要找到成本激增的根本原因，深入的 Kubernetes 可见性非常重要，它可以灵活地按名称空间、工作负载和节点细分成本，并通过利用率趋势追溯到特定的工作负载。通过将成本与节省成本的建议结合起来，透视可以直接找到成本的根本原因。CCM 提供了四种现成的透视图，可以根据用户需要灵活地创建定制透视图。

超越视角–引入定制仪表板

## 由商业智能(BI)支持的定制仪表板允许用户跨线束模块引入数据，并满足高级可视化、报告和警报用例的需求。用户可以在部署时间表的上下文中查看成本以及导致峰值的确切版本的根本原因，并在启用特定功能标记时预测成本增加。因此，使用多个 Harness 模块的客户可以灵活地在 Harness 中快速查看相关数据。

自定义控制面板的主要功能之一是创建自定义字段的灵活性。自定义字段本质上是由定义控制的计算字段，定义是支持的函数和第一类字段的组合。让我们看看一些用例以及带有相应可视化的定制字段示例。但是在深入示例之前，这里有一个示例中使用的字段和函数的快速概述:

$ { unified _ table . AWS _ GCP _ azure _ account _ project _ subscription }-->是在仪表板中显示以供使用的一级字段。CCM 公开了 50 多个一级字段来构造可视化。

case，when，matches_filter ->是 Harness BI 仪表板支持的函数的一个小子集，用于创建自定义字段。目前支持近 20 个函数来创建自定义字段。

示例 1:过滤具有特定命名约定的字段

### case(
when(matches _ filter($ { unified _ table . AWS _ GCP _ azure _ account _ project _ subscription }，`%ce% `)，
$ { unified _ table . AWS _ azure _ account _ project _ subscription })，
“其他”
)

这个定制字段本质上是一个正则表达式搜索，用于搜索子字符串为 **ce** 的所有帐户。任何没有此命名约定的帐户、项目或订阅都将被存储到*其他*中。任何具有特定命名约定的第一类字段与这些自定义字段配对可以简化仪表板并增强可视化。

示例 2:分时段成本

### 案例(
when(
$ { unified _ table . AWS _ GCP _ azure _ account _ project _ subscription } = " CCM-AWS "或
$ { unified _ table . AWS _ GCP _ azure _ account _ project _ subscription } = " CCM-GCP " " CCM ")，
when(
$ { unified _ table . AWS _ GCP _ azure _ account _ project _ subscription } = " FF-AWS "或
$ { unified _ table . AWS _ GCM

将各种帐户的成本归入成本桶的自定义字段。用于定义成本桶的字段可以跨云——GCP 产品、AWS 使用类型、Azure 订阅、标签、标记、Kubernetes 构造，如名称空间、工作负载名称、集群名称等。因此，自定义字段在定义成本时段时非常灵活。分桶对于创建业务上下文以及按产品、客户、成本中心、工程团队等划分的成本的可视化非常有用。以下是一个示例，说明如何使用分时段自定义字段向终端用户显示，以便在计划的报告和控制面板中使用:

定制仪表板还提供对云库存的深入了解，例如未充分利用的 [AWS 弹性计算(EC2)](https://aws.amazon.com/ec2/) 实例、孤立的 EBS 卷和快照等等。自定义控制面板是满足所有报告和自定义可视化需求的单一平台，并增加了自定义字段等功能的灵活性。

下一步是什么？

## 除了透视图和定制仪表板之外，CCM 将很快发布一个业务映射特性，该特性将允许您存储成本，并允许跨成本存储桶共享公共基础架构成本。敬请关注更多更新。

同时，你为什么不继续你的 CCM 阅读之旅呢？这里有几个建议: [BigQuery 在浪费的云支出上花费了令人震惊的 1.5 万美元](https://harness.io/blog/bigquery-wasted-cloud-spend/)和[云成本工作负载建议](https://harness.io/blog/recommendations-deep-dive/)。

同时，你为什么不继续你的 CCM 阅读之旅呢？这里有几个建议: [BigQuery 在浪费的云支出上花费了令人震惊的 1.5 万美元](https://harness.io/blog/bigquery-wasted-cloud-spend/)和[云成本工作负载建议](https://harness.io/blog/recommendations-deep-dive/)。