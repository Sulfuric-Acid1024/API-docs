# 个人信息

## 获取我的信息
> https://api.oiers.org/login/accout?client_id=&uid=


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
| data    | obj  | 信息本体 |                               |

`data`对象：
| 字段      | 类型 | 内容           | 备注                                    |
| --------- | ---- | -------------- | --------------------------------------- |
| uid       | num  | 我的uid        |                                         |
| userid    | str  | 我的用户名     |                                         |
| times      | str  | 我的注册日期   |                                         |
| level     | str | 账号等级        | 分为管理员(Admin)和普通用户(User)以及封禁用户（Banned)|

**示例：**

```shell
curl 'https://api.oiers.org/login/accout?client_id=&uid=' \
```

<details>
<summary>查看响应示例：</summary>
  
```json
{
    "status":1,
    "data":{
        "uid":1,
        "uname":"admin",
        "times":"2022-02-08 23:15"
        "level":"Admin"
    }
}
```
