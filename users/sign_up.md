中文描述：

接口描述：创建新用户

请求方式：POST

请求URL：[https://oiers.org/users/sign_up](https://oiers.org/users/sign_up)

POST参数：
|参数名|类型|描述|是否必选|备注|
|-----|----|----|-------|----|
|username|string|用户名|必选|不可与已有用户重复|
|passwd_h|string|hash后的用户密码|必选|用户密码hash方式为hb后sha512加密|
|hb_grade|uint|hash安全等级|必选|密码的hb hash等级|

返回信息(json encoded)：
|参数名|类型|描述|是否必选|备注|
|-----|----|----|-------|----|
|errorCode|uint|err码|一定存在|0000:成功<br/>1001:用户名重复|
|errorMes|string|err信息|一定存在|errorCode为1000时，为"succeeded"<br>errorCode为1001时，为"username used"|
|userID|uint|创建成功后产生的用户ID|一定存在|如果errorCode不为0000，则为0xFFFFFFFF(2147483647)|

English:

Use: Create an account

Method: POST

URL: [https://oiers.org/users/sign_up](https://oiers.org/users/sign_up)

POST parameters：
|Name|Type|Discription|Requireness|Other Information|
|-----|----|----|-------|----|
|username|string|Username of the user being created|Required|Can not be the same as an existing user|
|passwd_h|string|The password of the user after hash|Required|The method of hashing is an sha512 hash after hb hash|
|hb_grade|uint|Security grade for the hash|Required|Security grade for the hb hash for the password|

返回信息(json encoded)：
|Name|Type|Discription|Requireness|Other Information|
|-----|----|----|-------|----|
|errorCode|uint|error code|Required|0000:succeeded<br/>1001:username used|
|errorMes|string|error message|Required|When errorCode is 0000, the error message would be "succeeded"<br>When errorCode is 1001, the error message would be "username used"|
|userID|uint|The userID of the user created|Required|When errorCode is not 0000，userID would be 0xFFFFFFFF(2147483647)|
