# 短信

短信也是运营人员常用的一种营销方式，在合适的时间针对不同的用户发送不同的内容，传递企业产品的价值，用于促活、增加粘性。

## 使用前准备

短信适用于所有有帐号体系的平台，需要准备如下：

### 1. 集成方舟 SDK

发送短信时需要用户手机号，所以需要通过方舟SDK 上报用户手机号

### 2. 在方舟中选择短信服务商进行[服务集成配置](../project-manegement/project-integrations.md)

注：配置的过程中，需要选择上报为手机号的字段

![image](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172147142005.jpg)

## 功能说明

移入导航 **运营** 模块，选择进入 **短信** 页面

![image](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172148433807.jpg)

点击右上角 **立即创建**，进入创建页面

### 1. 创建短信

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172154432490.png)

**A. 消息名称**

用户自定义， 用于标识推送活动。

**B. 目标用户**

支持从下拉框中选择已圈定好的目标分群。

![&#x63A8;&#x9001;&#x76EE;&#x6807;](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901171607599092.jpg)

对于选定的分群支持显示有效用户数，因为发送短信需要手机号，所以圈定的目标分群中若包含没有手机号的用户，在推送时将进行过滤。

![&#x63A8;&#x9001;&#x76EE;&#x6807;](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172156117531.png)

**C. 发送通道**

使用之前，需要进行推送配置接入短信服务商。目前方舟预置了乐信通，如有需要可以自定义或者联系我们增加

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901181611231250.png)

**D. 发送短信**

运营商规定，短信需经过审核通过后方可发送，所以发送短信前需要先创建审核通过的短信模型。

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901181017035536.png)

方舟支持从各短信通道同步短信模板及其审核状态，但对于部分通道，比如乐信通不支持相应API，如需使用，需要手动从短信平台上复制粘贴到方舟当中进行模板配置。

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172208467312.gif)

发送时直接选择模板

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172159484446.png)

**E. 推送时间**

![ ](https://imguserradar.analysys.cn/fangzhou/img/2018/08/201808101745487832.png) 有立即推送、定时推送和周期性推送三种

* **立即推送**，确认发送即时生效
* **定时推送**，可设定日期、时间准时发送
* **周期性推送**，以日/周/月的周期重复发送，可以设置开始和结束时间

**G. 草稿、发送**

编辑好的内容点击确认推送，即可开始的推送；也可以存为草稿。

![ ](https://imguserradar.analysys.cn/fangzhou/img/2018/08/201808101759154861.png)

### 2. 短信消息列表

所有已创建的消息会显示在列表中

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172213044964.png)

列表当中会包含以下状态的消息： ![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172217519929.png)

* **待推送**：设置了定时或者周期性推送消息，且没有到达相应时间是，消息为待推送状态
* **推送中**：正在推送当中的消息
* **推送成功**：推送完成的消息
* **推送失败**：因为通道错误、接口错误等导致的推送失败
* **停止推送**：对于定时或者周期性消息，在推送前点击停止推送的消息
* **草稿**：还没有确认推送的草稿

支持操作包括：

A. 通过关键字快速搜索

B. 通过时间段过滤

C. 编辑草稿消息

D. 删除消息

E. 另存为

F. 停止推送（仅支持停止未开始推送的定时或者周期性消息）

G. 查看发送效果

### 3. 效果分析

发信的实际发送情况，可以从列表中进入查看，主要指标：

* 目标用户：只圈定的用户群
* 有效用户：其中有手机号的用户
* 发送成功用户：短信通道发送成功的用户
* 接收成功用户：电信运营商返回接收成功的用户

![ ](https://imguserradar.analysys.cn/fangzhou/img/2019/01/201901172214135028.png)

## 常见问题

**Q1. 易观方舟负责推送吗？到达率在什么水平？**

易观方舟关注的是如何将第三方的推送服务和方舟的分析结合，使得分析得以通过触达落地，从中起到的是连接作用。您可以在方舟中创建推送的内容，但是推送消息本身通过第三方的推送平台来实现，到达率也取决于各个推送平台。

**Q2. 是否还需要单独购买第三方服务？**

取决于第三方推送平台是否收费。若其免费，则需在第三方推送服务平台上注册账号、添加应用，获取相应的AppKey等，集成推送SDK，并在方舟的 **管理-推送配置** 中完成绑定。

**Q3. 支持同时使用多家推送服务？**

目前支持多家服务融合使用。

**Q4. 短信的效果是怎么监测的？**

目前只能监测到以下四个指标，若短信中带有链接，其点击情况的追踪，目前还在开发中。

* 目标用户：只圈定的用户群
* 有效用户：其中有手机号的用户
* 发送成功用户：短信通道发送成功的用户
* 接收成功用户：电信运营商返回接收成功的用户

**Q5. 正在使用的推送服务没有出现在支持列表中，怎么办？**

请致电 **4006-010-231** 与我们联系。
