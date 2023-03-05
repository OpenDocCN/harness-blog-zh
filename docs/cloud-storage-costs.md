# 云存储:看不见的成本|利用

> 原文：<https://www.harness.io/blog/cloud-storage-costs>

了解这些云存储选项使团队能够为他们的云存储用例在成本、质量和速度之间做出有意识的权衡决策。

迁移到公共云的现实是，它不符合降低运营成本的预期。除了这种绝望，组织还在努力寻找云成本的主要贡献者。因此，对云成本的担忧并不奇怪，ZDNet 的文章[证实了云成本控制成为企业的首要问题](https://www.zdnet.com/article/cloud-cost-control-becoming-a-leading-issue-for-businesses/#:~:text=The%20concern%20about%20cloud%20costs%20is%20not%20surprising.&text=IDC%20reckons%20that%20global%20public,services%20will%20hit%20%24370%20billion.)。该文章认为，到 2022 年，全球公共云服务和基础设施支出将达到价值 3700 亿美元的市场。释放云的优势可以让云客户变得更加敏捷、安全和协作，但服务、工具和其他附加组件会迅速导致成本上升。

云存储是云成本的主要来源。在《财富商业洞察》进行的一项研究中，2019 年估计为 491.3 亿美元的云存储市场到 2027 年将达到 2975.4 亿美元。随着云客户迈向人工智能、机器学习和物联网，存储成本只会继续增长。根据 Flexera 的 2019 年云状态报告，2019 年的首要云计划是优化云资源的现有使用，以节省成本。为了节省云存储成本，这篇博客文章将解释云存储服务和成本的基础知识。

## **存储服务:**

公共云解决方案提供一系列服务来存储、访问、管理和分析数据。在 AWS 中，这表现为对象存储、文件存储、数据块存储以及在云中迁移或备份数据的解决方案。

### **AWS 中的存储类型有哪些？**

亚马逊 EFS、亚马逊 EBS 和亚马逊 S3 是 AWS 的三种不同的存储解决方案。让我们更详细地讨论每一个问题。

存储服务 ServiceAMAZON S3AMAZON EBSAMAZON 功能可公开访问对象存储 Web 接口可扩展低于 EBS 和 EFS 只能通过给定的 EC2 机器文件系统接口访问块存储可扩展速度比 S3 和 EFS 快可通过几台 EC2 机器访问对象存储可扩展速度比 S3 快，比 EBS 慢适合存储备份作为 EC2 存储卷很好适合可共享的应用程序和工作负载无服务器文件存储马云 S3 VS EBS VS EFS。

亚马逊简单存储服务(亚马逊 S3)是在一个扁平的、无层次的环境中存储对象的解决方案。每个对象文件都包含一个唯一的标识符键，因此可以通过 web 请求从任何服务访问该对象。文件最多只能有 5TB 的数据。

亚马逊的弹性块存储(EBS)是针对云计算实例(如亚马逊 EC2 实例)的块级存储。它们充当存储卷，类似于用于机器的本地磁盘驱动器。有不同类型的卷，包括固态驱动器(SSD)和硬盘驱动器(HDD)。

*   有两种固态硬盘 EBS:
*   IOPS 固态硬盘(io1) -最高性能的固态硬盘卷，专为延迟敏感型工作负载而设计。用例:NoSQL 和关系数据库
*   EBS 通用固态硬盘(gp2)* -平衡价格和性能的容量。用例:低延迟交互式应用、开发和测试。
*   还有两种类型的硬盘 EBS
*   吞吐量优化硬盘(st1) -低成本硬盘卷，适用于频繁访问的吞吐量密集型工作负载。用例:大数据和日志处理。
*   冷硬盘(sc1) -成本最低的硬盘卷，适用于访问频率较低的工作负载。用例:每天需要少量扫描的数据。

亚马逊弹性文件系统(EFS)是一种文件系统存储服务，用于扩展和管理延迟敏感的存储需求。亚马逊 EFS 卷被装载到各种 AWS 服务上，并且可以被多个虚拟机访问。这非常适合运行服务器、共享卷、大数据分析和其他可扩展工作负载。

了解这些云存储选项使团队能够为他们的云存储用例在成本、质量和速度之间做出有意识的权衡决策。因此，让我们讨论一下与成本相关的云存储。

## **云存储定价**

管理和优化成本的一个核心原则是将成本视为一个效率指标。有四个组成部分，包括云存储定价、存储成本、请求和数据检索成本、数据传输成本以及功能管理和复制成本。某些类型的存储服务不存在这些成本。

**存储服务**亚马逊 S3AMAZON EBSAMAZON EFS **存储**✔
gb-month✔
gb-month✔
每 GB 月**请求和数据检索** ✔
每 GB 或每 1，000 个请求 sN/AN/A **数据传输**每 GB 从亚马逊 s3N/AN/A **管理和复制** ✔
每 GB

亚马逊 EBS 定价比亚马逊 S3 定价简单，您只需支付每月每 GB 的存储和管理快照的成本。亚马逊 EFS 有最简单的定价结构，因为你只需要选择一个 EFS 类(Stand 或 EFS IA，很少访问)并为你使用的东西付费。

## **数据库云服务怎么样？**

我建议将这篇博文中分享的原则应用于数据库云服务。亚马逊的关系数据库服务(RDS)成本也基于不同的实例、层和使用。这些情况的定价各不相同，通常存储费用是每月每 GB，但在其他情况下，可以按小时收费。云存储成本的四个组成部分也适用于数据库云服务成本。了解这些服务的成本差异是优化云支出的绝佳起点。

## **总结**

FinOps 团队可以消除工程师和运营团队关注云内费率谈判的需要，相反，他们应该关注云的使用优化和可变成本模型。这篇博文分享了云存储服务背后的关键概念。优化是指通过了解云支出、利用率和资源消耗，不断调整云的使用和优化。Harness 的[云成本管理](https://harness.io/platform/cloud-cost-management/)产品可以帮助您在公共云中做到这一点。了解有关云成本管理的更多信息，并[立即申请演示](https://harness.io/platform/cloud-cost-management/)。

**资源:**

[https://aws.amazon.com/s3/](https://aws.amazon.com/s3/)

[https://aws.amazon.com/efs/](https://aws.amazon.com/efs/)

[https://aws.amazon.com/ebs/](https://aws.amazon.com/ebs/)