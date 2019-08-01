---
description: 大型企业内部需要很严格地执行安全相关的规范，账号安全设置是其中重要的部分。
---

# 安全设置

![](../../.gitbook/assets/image%20%2879%29.png)

默认展示当前安全设置状态，管理员可以同点击【修改】按钮进行自身需求的设置

![](../../.gitbook/assets/image%20%2893%29.png)

进入设置页可以根据自身对安全需求的高、中、低选择相应的快捷设置，也可以自定义设置。



| 功能 | 选择 | 安全等级-高 | 安全等级-中  | 安全等级-低 | 显示 | 是否屏蔽系统管理员 | 是否屏蔽其他人员 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 密码长度 | x | 8 | 6 | 6 | 密码长度必须大于等于 x位 字符 | 否 | 否 |  |
| 密码有效期 | x | 90 | 180 | 365 | 密码必须每 x天 修改一次 | 否 | 否 | 超过有效期将被锁定；解锁后，密码有效期重新开始计算 |
| 曾用密码 | x | 10 | 5 | 3 | 不能使用过去使用过的 x个 密码 | 否 | 否 |  |
| 强制修改 | 必须 | 要求 | 要求 |  | 用户首次登录系统或管理员重置密码后第一次登录，密码 必须 强制修改 | 是 | 否 |  |
| 强制修改 | 不必 |  |  | 要求 | 用户首次登录系统或管理员重置密码后第一次登录，密码 不必 强制修改 | 是 | 否 |  |
| 初始密码 | x | 90 | 180 | 365 | 添加账户后，初始密码超过 x天 未作修改，账号将被锁定 | 是 | 否 | 解锁后，密码有效期重新开始计算 |
| 连续登陆失败 | x | 5 | 8 | 10 | 连续登陆失败 x次 后账号将会被锁定 | 否 | 否 | 解锁后，登录有效期不变 |
| 帐号登录有效期 | x | 90 | 180 | 365 | 账号连续 x天 没有登录过，帐号将被锁定 | 否 | 否 | 解锁后，密码有效期重新开始计算 |
| 重新登录 | x | 30 | 720 | 1440 | 登录后超过 x分钟 没操作，将强制重新登录 | 否 | 否 |  |
