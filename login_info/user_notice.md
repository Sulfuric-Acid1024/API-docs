# 登录记录

> https://api.oiers.org/account/user_notice


*请求方式：GET*

认证方式：Cookie

**url参数：**
| 参数名 | 类型 | 内容       | 必要性 | 备注                                                         |
| ------ | ---- | ---------- | ------ | ------------------------------------------------------------ |
| uid    | num  | 用户uid    | 必要   |                                                              |
| client_id  | str  | hash | 必要 | 认证 |
| user-agent | str  | 设备信息 | 必要 | 记录设备信息 |


**json回复：**

根对象：
| 字段    | 类型 | 内容     | 备注                        |
| ------- | ---- | -------- | --------------------------- |
| code    | num  | 返回值   | 0：成功<br />-101：账号未登录<br />-400：请求错误 |
| data    | obj  | 信息本体 |                             |

`data`对象：
| 字段        | 类型 | 内容        | 备注                       |
| ----------- | ---- | ----------- | -------------------------- |
| uid         | num  | 登录用户mid |                            |
| user-agent | str  | 登录设备    | 依靠操作登录接口时的UA决定 |
| login_time  | str  | 登录时间    | YYYY-MM-DD hh:mm:ss        |
| location    | str  | 登录位置    | 依靠ip决定                 |
| ip          | str  | 登录ip      |           |

**示例：**

查询用户UID为`1`的登录记录

```shell
curl -G 'https://api.oiers.org/account/user_notice' \
--data-urlencode 'uid=1' \
```

<details>
<summary>查看响应示例：</summary>

```json
{
    "code": 0,
    "data": {
        "uid": 1,
        "device_name": "Mozilla/5.0 (Windows NT 10.0; rv:91.0) Gecko/20100101 Firefox/91.0",
        "login_time": "2020-10-02 22:42:38",
        "location": "美国",
        "ip": "2600:3c01::f03c:93ff:fe6e:ec9b"
    }
}
```

</details>
