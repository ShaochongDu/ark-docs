---
description: 本文档中描述的内容，主要针对熟悉SQL的数据分析师或技术人员，如果对文档内容有疑惑，请咨询我们。
---

# 自定义查询

## 自定义查询

如果使用方舟现有的分析功能无法满足您的分析需求，或者您想通过SQL来进行更加灵活的数据分析并导出结果，您可以使用我们提供的自定义查询工具。该工具还可以针对查询结果生成图表完成可视化分析。

{% hint style="info" %}
该工具从方舟4.2.2版本开始提供，如果您的版本还没有该工具，您可以升级方舟到4.2.2版本来进行体验。
{% endhint %}

### 1. 工具入口

进入方舟后在当前项目下 选择【分析 - 自定义查询】即可打开方舟自定义查询工具。

自定义查询工具界面如下图：

![](../../.gitbook/assets/image%20%2821%29.png)

{% hint style="info" %}
易观方舟自定义查询工具只能查询您当前正在使用的项目。如果您在方舟中切换了项目，可以按上述步骤重新点击“自定义查询”打开新的自定义查询工具窗口。
{% endhint %}

### 2. 数据表

在自定义查询工具中只能看到您当前在方舟中访问的项目的表，目前有**event\_vd（事件表）**和**profile\_vd（用户表）**，未来还会支持导入客户自定义的其它辅助数据表。

#### 2.1 查看表结构

然后进入PrestoSQL，即可看到当前项目的库名、表名和字段信息。查看步骤如下：

![](../../.gitbook/assets/image%20%2816%29.png)

#### 2.2 字段说明

**2.2.1 event\_vd （事件表）**

事件表包含了所有事件的详细信息（不包括虚拟事件），该表中存储了所有用户的行为数据，表中的每一行都是一个行为记录。该表中的字段主要分为两类：事件本身的特殊字段和普通的属性字段。

事件特殊字段如下：

| 字段 | 说明 | 示例 |
| :--- | :--- | :--- |
| distinct\_id | 易观方舟为该用户分配的内部 ID，与 profile\_vd 表的 distinct\_id 字段相关联 | 599898980 |
| xwho | 用户行为发生的原始ID，可以为注册用户ID或临时ID | lurenjian |
| xwhen | 用户行为发生的时间，精确到毫秒 | 1552220964474 |
| xwhat | 用户行为名称 | $pageview |
| ds | 用户行为发生的日期，精确到天 | 20190210 |

{% hint style="info" %}
distinct\_id并不是真正的用户ID，而是易观方舟基于用户真实ID生成的用于唯一标识一个用户的ID，详细说明请参见《[如何准确识别用户](../../integration/prepare/user-identify.md)》
{% endhint %}

**2.2.2 profile\_vd（用户表）**

用户表的每一行代表一个 用户，类似于事件表，用户表的字段也分为特殊字段和用户的其它 属性两大类，其中特殊字段的说明如下：

| 字段 | 说明 | 示例 |
| :--- | :--- | :--- |
| distinct\_id | 易观方舟为该用户分配的内部 ID，与 profile\_vd 表的 distinct\_id 字段相关联 | 599898980 |
| xwho | 用户行为发生的原始ID，可以为注册用户ID或临时ID | lurenjian |

### 3. 功能使用

#### 3.1 基本功能使用

直接在SQL输入框中写SQL即可，注意一次只能执行一条SQL，而且**SQL的未尾不能加分号。**

下图示例查询每天的事件量:

![](../../.gitbook/assets/image%20%2873%29.png)

默认情况下以表格的方式展示结果，为了优化性能，页面最多展示1000条数据，如果您需要查更多的数据，可以将结果下载下来，最多只能下载100w数据。如果您想下载更多数据，请使用数据导出的方式通过api来下载。

**3.1.1 图表展示**

![](../../.gitbook/assets/image%20%2810%29.png)

如上图，选择以图表的方式展示数据，支持多种图表。

**3.1.2 下载数据**

自定义查询工具支持将查询结果下载，当查询结果数据量大于1000时，页面为了性能考虑只展示1000条，但下载结果时最多可下载100w数据。

![](../../.gitbook/assets/image%20%2826%29.png)

结果下载支持菜单栏中的CSV和Excel指下载的文件格式，如果结果数据量大，建议您尽量下载CSV格式，CSV格式在相同数据量的情况下文件更小，下载更快。

Clipboard指将下载结果复制到粘贴板，您可以在其它文件编辑器里“粘贴”操作，即可将结果粘贴到其它编辑器中。

#### 3.2 使用优化

ds字段是日期字段，您可以使用ds字段过滤数据。为了提高查询性能，请您尽量在SQL中添加ds字段过滤，只查询需要的数据。

易观方舟使用的查询引擎是presto，关于presto的Date和Time类型的函数可以参考presto的官方文档：[https://prestodb.github.io/docs/0.201/functions/datetime.html](https://prestodb.github.io/docs/0.201/functions/datetime.html)
