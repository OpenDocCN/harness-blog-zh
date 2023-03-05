# 使用 Harness | Harness 实现连续交付的民主化

> 原文：<https://www.harness.io/blog/democratizes-continuous-delivery-using-harness>

了解 Lessonly 如何将部署工作负载分配给其开发人员。

## **关于**

Lessonly 是一个非常简单的培训软件，可以帮助团队学习、练习和做得更好。它们使繁忙的团队能够达成一致，走在变革的前面，并为客户和潜在客户提供令人惊叹的体验。在 Lessonly.com 了解更多信息。

## **舒服的不一定是最好的**

Lessonly 将其应用程序托管在 Heroku，有一段时间，生活是美好的。Heroku 提供了开发人员用来部署其服务的部署工具。但是随着 Lessonly 的发展，站点可靠性工程师 Stephen Gregory 和 Tyler Henrichs 遇到了问题。Heroku 缺乏基础设施灵活性和治理功能，而且随着应用程序数量的增长，Heroku 的定价结构成倍增加了托管成本。

Stephen 和 Tyler 花了几个月的时间来维护 Heroku 并解决问题。两人决定是时候找到更好的解决方案了。该解决方案将提供高级 RBAC 功能、更多的审计跟踪，并帮助开发人员培养“自助式”部署文化。

我们希望创造一种部署文化，让开发人员对自己的服务负责。

> 泰勒·亨利希| SRE |莱斯 only

## **试错**

面对日益增加的 Heroku 费用，Lessonly 决定迁移到 AWS。Stephen 和 Tyler 需要想出如何部署新的 AWS 应用程序。

该团队开始试验基于 Jenkins 和 Spinnaker 的管道。这些弗兰肯斯坦管道使用 Jenkins 构建工件，使用 Spinnaker 将工件部署到生产中。在他们的实验中，泰勒和斯蒂芬发现一项服务需要一整周的时间。Tyler 和 Stephen 还估计使用这些工具构建部署解决方案需要整整 6 个月的时间，即使 6 个月后，他们仍然缺少 RBAC 和审计跟踪。他们都认为提供一个平庸的解决方案不是一个选择。

如果我们试图构建自己的部署解决方案，我们会降低开发人员的体验。我们没打算那么做。

> 斯蒂芬·格雷戈里| SRE 校长|莱斯 only

## **线束输送**

很明显，詹金斯-三角帆组合不能满足它的要求，Lessonly 转向了利用。Harness 为开发人员提供了对自己服务的部署所有权，并且开箱即用，具有高级 RBAC 和审计功能。Lessonly 的开发人员惊讶于它的易用性。

开发人员认为他们必须学习 AWS 和 Kubernetes，但实际上，他们只需要定义代码是如何发布的。花了他们一天时间。

> 斯蒂芬·格雷戈里| SRE 校长|莱斯 only

以前需要一整周的时间来安装一项新服务，现在只需几分钟就可以完成。斯蒂芬和泰勒再也不用担心维护时间了。Stephen 和 Tyler 利用新获得的空闲时间，将更多资源投入 Lessonly 的应用程序，而不是将该应用程序投入生产。

转向脊甲最大的好处是什么？几乎没有一个开发者注意到这种转变。

我们改变了系统，改变了一切运作的方式。没人注意到。这是最大的褒奖。

> 斯蒂芬·格雷戈里| SRE 校长|莱斯 only