# 使用账号密码登录

> http://api.oiers.org/login/v1

*请求方式：POST*

验证登录成功后会进行设置以下Cookie项：

`__client_id` `_uid`   `times` 

| Cookie名称      | 类型 | 内容             | 必要性 | 备注             |
| ----------- | ---- | ---------------- | ------ | ---------------- |
| __client_id | str  | hash              | 必要   | 验证登录        |
| _uid    | str  | 用户id     | 必要   |  |
| times     | str  | 登录时间         | 非必要   | 从本地读取       |
