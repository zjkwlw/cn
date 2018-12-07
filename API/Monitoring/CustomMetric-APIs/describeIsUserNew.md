# describeIsUserNew


## 描述
查询是否是新用户

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/cm/users/isNew


## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**result**|Boolean|是否新用户|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询该用户是否是新用户|
