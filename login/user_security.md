# 账号安全

## 查询账号安全情况
> https://api.oiers.org/user/security?client_id=&uid=

*请求方式：GET*

认证方式：Cookies

| Cookie名称      | 类型 | 内容             | 必要性 | 备注             |
| ----------- | ---- | ---------------- | ------ | ---------------- |
| client_id | str  | hash              | 必要   | 验证登录        |
| uid    | str  | 用户id     | 必要   |  |


**json回复：**

根对象：
| 字段    | 类型 | 内容     | 备注                          |
| ------- | ---- | -------- | ----------------------------- |
| status    | bool  | 返回值   | 1为成功，0为失败 |
| data    | obj  | 信息本体 |     

`data`对象：

| 字段          | 类型 | 内容             | 备注 |
| ------------- | ---- | ---------------- | ---- |
| account_info  | obj  | 账号绑定信息     |      |
| account_safe  | obj  | 密码安全信息     |      |
| account_sns   | obj  | 登录绑定信息 |      |

`data`中的`account_info`对象：

| 字段               | 类型 | 内容           | 备注                            |
| ------------------ | ---- | -------------- | ------------------------------- |
| hide_mail          | str  | 绑定的邮箱     | 星号隐藏部分信息                |
| bind_mail          | bool | 是否绑定邮箱   | false：未绑定<br />true：已绑定 |
| mail_verify        | bool | 是否验证邮箱   | false：未验证<br />true：已验证 |
| unneeded_check     | bool | 是否未设置密码 | false：已设置<br />true：未设置 |

`data`中的`account_safe`对象：

| 字段      | 类型 | 内容             | 备注                          |
| --------- | ---- | ---------------- | ----------------------------- |
| pwd_longs  | num  | 设置密码长度   | |
| pwd_level | num  | 当前密码强度等级 | 1：弱<br />2：中<br />3：强   |
| security  | bool | 当前密码是否安全 | false：不安全<br />true：安全 |

`data`中的`account_sns`对象：

| 字段        | 类型 | 内容         | 备注                     |
| ----------- | ---- | ------------ | ------------------------ |
| github_bind  | bool  | 是否绑定github | 0：未绑定<br />1：已绑定 |
