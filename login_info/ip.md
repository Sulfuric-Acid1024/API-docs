# 记录操作IP

> https://api.oiers.org/web-interface/zone


*请求方式：GET*

**json回复：**

根对象：
| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| status   | bool  |    | 1：成功 |
| data    | obj  | 信息本体 |         |

`data`对象：
| 字段         | 类型 | 内容          | 备注         |
| ------------ | ---- | ------------- | ------------ |
| IP         | str  | 公网IP地址    |              |
| country      | str  | 国家/地区名   |              |
| province     | str  | 省/州         | 非必须存在项 |
| city         | str  | 城市          | 非必须存在项 |
| country_en | num  | 国家/地区代码 |              |

**示例：**
```shell
curl 'https://api.oiers.org/web-interface/zone'
```
<details>
<summary>查看响应示例：</summary>

```json
{
    "code":0,
    "message":"0",
    "ttl":1,
    "data":{
            "addr":"2600:3c01::f03c:93ff:fe6e:ec9b",
            "country":"美国",
            "country_code":US,
        }
}
```
</details>
