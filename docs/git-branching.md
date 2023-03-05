# 线束中的 Git 分支|线束

> 原文：<https://www.harness.io/blog/git-branching>

Git 分支提供了一种简单的方法来进行配置更改，并减少了开发、测试和维护 CI/CD 管道的时间。找出方法。

版本控制系统引入了跟踪文件版本的概念，并通过分支、修改、测试，然后在批准和 CI 检查后合并到主分支来单独进行更改。

Git 体验支持分支概念，在这种情况下，我们可以遵循类似的线束实体范例，如管道、连接器等。我们可以从主分支分叉，在不破坏其他分支的情况下进行更改，隔离测试，然后将其合并回主分支——就像任何其他代码更改一样。

要求

## 我们对 Git 分支有以下要求:

丰富的用户体验，每种实体类型都有单独的部分。

1.  支持实体的分页和高级过滤。
2.  渲染实体的低延迟。
3.  提供相同的体验，即使禁用了 Git 体验。
4.  挑战和解决方案

## 为了满足这些要求，我们面临以下挑战:

Git 是基于文件系统的存储。要在每次有人提供过滤器时从 Git 中检索数据，您必须扫描 Git 中的所有文件，然后解析它们以满足 UI 请求。这将导致长时间的等待。

*   即使我们将 Git 的状态保持在利用中，将从 Git 到利用的变化*对齐也是一个挑战。*
*   用户可以在不改变配置的情况下继续创建分支，有时他们不希望这些分支处于束缚中。
*   作为缓存的 MongoDB

### 为了优化，我们使用 Mongo 作为缓存，解析所有的实体，并将它们保存在数据库中。这让我们克服了从 g it 获取数据时可能会遇到的性能瓶颈。

Git Webhooks

### 因为所有的 Git 提供者都有针对 Git 上不同事件的 webhooks，所以我们用它们来更新我们的 Mongo。一旦启用了 Git 体验，我们就在 Git 中自动注册 webhook。这导致 Harness 在 Git 中接收不同种类的事件。

收到事件后，我们将它们排队，然后异步更新我们的系统。例如，当我们收到一个分支创建事件时，我们更新显示在 UI 中的分支列表。类似地，当我们收到一个分支删除事件时，我们从 Harness Mongo 缓存中删除该分支。此外，当我们接收到推送事件时，我们获取提交中每个文件的内容，并更新线束实体。

为了优化分支和回购过滤器，我们将它们与其他数据一起存储在我们的实体中。

分行入围名单

### Git 中任何新分支的创建并不总是意味着配置的改变。我们提供按需同步，以防用户想要同步特定分支。在触发同步时，我们提取该分支的每个实体，解析它们，然后将它们存储在 Mongo 中。

用户体验

## 我们为想要从 Harness UI 添加/修改实体的用户提供了类似于 git 提供者的用户体验。

Git 操作的用户凭据

### 为了识别用户对 Harness 的提交，我们使用了用户概要的概念。在用户配置文件下，我们有一个源代码管理器，用户必须提供他们的个人访问令牌来对 Git 进行任何更改。SCM 对于审计对项目及其管道、连接器等进行变更的人员非常有用。这也有助于遵守回购中设定的分支规则。

分支分叉和 PR 创建

### 当从 Harness UI 推送至 Git 时，我们为用户提供了推送至新分支或现有分支的能力，以及创建 PR。这将有助于用户分叉分支，并在合并之前得到审查。此外，这将允许其他人继续从主分支处理管道，而配置更改仍在审查中。

实体列表

### 为了让用户在多回购场景下有一个无缝的体验，我们列出了默认的分支实体，然后用户可以按回购分支筛选得到实体。此外，在多个分支的情况下，用户可以对任何分支进行筛选，查看所有实体，并应用高级筛选器。

跨分支机构交换实体

### 为了在分支之间无缝切换并进行比较，我们允许用户在任何实体的细节部分切换分支。

结论

Pipeline in Main Branch

Same Pipeline in Develop Branch

## Git 同步和 Git 分支为现代 DevOps 解决方案带来了巨大的潜力。它们提供了一种简单的方法来进行配置更改，并帮助开发人员减少开发、测试和维护 CI/CD 管道的总时间。特别是，分支可以让一个分支中的所有配置变更在投入生产之前被隔离测试。此外，它使他们不会因为不正确的配置更改而阻止任何人。

和我们一起推进你的阅读之旅！看看我们是如何利用 [GitOps](https://harness.io/blog/harness-gitops-deployments/) 的。如果你错过了姐妹文章， [Git 同步体验](https://harness.io/blog/git-sync-experience/)，现在可以随意阅读。

*本文由阿比纳夫·辛格、阿卡什·纳加拉詹、拉玛·图马拉和迪帕克·帕坦卡尔合作撰写。*

*本文由阿比纳夫·辛格、阿卡什·纳加拉詹、拉玛·图马拉和迪帕克·帕坦卡尔合作撰写。*