# 通过账号密码登录

## 获取加密公钥及密码盐值

> https://api.oiers.org/login

*请求方式：GET*

**json回复：**

根对象：

| 字段 | 类型 | 内容         | 备注             |
| ---- | ---- | ------------ | ---------------- |
| hash | str  | 密码校验盐值 | 有效时间为30s    |
| times | int | 读取时间    | |
| key  | str  | RSA公钥      | **公钥为固定值** |

**示例：**

```shell
curl 'http://api.oiers.org/login'
```

<details>
<summary>查看响应示例：</summary>

```json
{

    "hash":"8e0db05c46f4052c",
    "key":"-----BEGIN PUBLIC KEY-----\nMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDjb4V7EidX/ym28t2ybo0U6t0n\n6p4ej8VjqKHg100va6jkNbNTrLQqMCQCAYtXMXXp2Fwkk6WR+12N9zknLjf+C9sx\n/+l48mjUU8RqahiFD1XT/u2e0m2EN029OhCgkHx3Fc/KlFSIbak93EH/XlYis0w+\nXl69GV6klzgxW6d2xQIDAQAB\n-----END PUBLIC KEY-----\n"

}
```
