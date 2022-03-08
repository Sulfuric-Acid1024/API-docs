## 提交注册请求

> http://api.oiers.org/user/signup

*请求方式：POST*

**正文参数（ application/x-www-form-urlencoded ）：**
| 参数名 | 类型 | 内容 |
| --- | --- | --- |
| Username | str | 用户名 |
| code | num | 邮箱验证码 |
| pwd | str | 密码 |
| jumpurl | str | 注册成功跳转地址 |
| mail | str | 邮件地址 |
| plat | num | 0为Web端注册，1为手机端注册（根据User-Agent识别） |

**json回复：**

根对象：
| 字段   | 类型 | 内容     | 备注         |
| ------ | ---- | -------- | --------- |
| code | num | 返回值 | 0:成功<br>-1:验证码错误<br>666:验证码过期 |
| data | obj | 成功信息 | 只在成功时存在 |
| error | str | 错误信息 | 只在错误时存在 |

成功信息
| 字段   | 类型 | 内容     | 备注         |
| ------ | ---- | -------- | --------- |
| redirectUrl | str | 跳转链接 |  |
| hint | str | "注册成功" |  |

<details>
<summary>查看示例</summary>
  
```bash
curl 'http://api.oiers.org/user/signup' \
    -X POST \
    -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:91.0) Gecko/20100101 Firefox/91.0' \
    -H 'Accept: application/json, text/plain, */*' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    --data-raw 'Username=admin&code=562395&pwd=MSSyD2nKHaTG&jumpurl=https://dash.oiers.org&mail=test@gmail.com&plat=0'
```
</details>
