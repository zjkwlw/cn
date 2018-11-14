## 描述
创建应用

## 限制
每个账户下支持创建最多20个应用

## 请求方式
POST

## 请求地址
https://ias.jdcloud-api.com/v1/regions/{regionId}/app

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域编码，参考《公共说明》|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**accessTokenValiditySeconds**|Integer|False| |访问令牌有效期，单位：秒，范围：10分钟到6小时（即600秒到21,600秒）|
|**account**|String|False| |account|
|**clientName**|String|False| |应用名|
|**clientUri**|String|False| |clientUri|
|**contacts**|String|False| |contacts|
|**extension**|String|False| |extension|
|**grantTypes**|String|False| |grantTypes|
|**jwks**|String|False| |jwks|
|**jwksUri**|String|False| |jwksUri|
|**logoUri**|String|False| |logoUri|
|**multiTenant**|Boolean|False| |multiTenant|
|**policyUri**|String|False| |policyUri|
|**redirectUris**|String|False| |redirectUris|
|**refreshTokenValiditySeconds**|Integer|False| |refreshTokenValiditySeconds|
|**scope**|String|False| |scope|
|**secret**|String|False| |secret|
|**secretUpdateTime**|Integer|False| |secretUpdateTime|
|**tokenEndpointAuthMethod**|String|False| |tokenEndpointAuthMethod|
|**tosUri**|String|False| |tosUri|
|**userType**|String|False| |userType|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String| |
|**result**|Result|创建app返回结果|

### Result
|名称|类型|描述|
|---|---|---|
|**accessTokenValiditySeconds**|Integer|accessTokenValiditySeconds|
|**account**|String|account|
|**clientId**|String|应用|
|**clientName**|String|应用名|
|**clientUri**|String|clientUri|
|**contacts**|String|contacts|
|**extension**|String|extension|
|**grantTypes**|String|grantTypes|
|**jwks**|String|jwks|
|**jwksUri**|String|jwksUri|
|**logoUri**|String|logoUri|
|**multiTenant**|Boolean|multiTenant|
|**policyUri**|String|policyUri|
|**redirectUris**|String|redirectUris|
|**refreshTokenValiditySeconds**|Integer|refreshTokenValiditySeconds|
|**responseTypes**|String|responseTypes|
|**scope**|String|scope|
|**secretUpdateTime**|Integer|secretUpdateTime|
|**tokenEndpointAuthMethod**|String|tokenEndpointAuthMethod|
|**tosUri**|String|tosUri|
|**userType**|String|userType|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**404**|NOT_FOUND|
