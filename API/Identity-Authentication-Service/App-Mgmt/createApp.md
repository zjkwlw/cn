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
|**clientName**|String|True| |应用名|
|**redirectUris**|String|True| |回调地址，最多4个，多个url之间用逗号,分隔，每个url长度不超过1000，url不支持#符号|
|**grantTypes**|String|True| |支持的OAuth类型：<br/>authorization_code：OAuth2授权码模式<br/>implicit：OAuth2隐式授权模式<br/>refresh_token：启用刷新令牌<br/><br/>grantTypes支持以下值：<br/>（1）authorization_code<br/>（2）authorization_code,refresh_token<br/>（3）authorization_code,implicit<br/>（4）authorization_code,implicit,refresh_token<br/>（5）implicit<br/><br/>注：如果grantTypes指定了refresh_token，应用将可以使用刷新令牌；如果在创建应用时未指定，则应用不能使用刷新令牌；任何时候应用都可以调用“更新应用”接口更改grantTypes设置|
|**tokenEndpointAuthMethod**|String|True| |客户端认证方式：<br/>none：不设置客户端密码（不推荐）<br/>client_secret_post：客户端必须设置密码，且该密码需要在 OAuth2 Token Endpoint 提供于请求的 body<br/>client_secret_basic：客户端必须设置密码，且该密码需要在 OAuth2 Token Endpoint 提供于请求的 header<br/><br/>支持以下值：<br/>（1）none<br/>（2）client_secret_post<br/>（3）client_secret_basic|
|**accessTokenValiditySeconds**|Integer|True| |访问令牌有效期，值的范围为 600 秒到 6x3600=21,600 秒，即10分钟-6小时|
|**refreshTokenValiditySeconds**|Integer|False| |刷新令牌有效期，值的范围为 30x24x3600=2,592,000 秒到 365x24x3600=31,536,000 秒，即30天-365天<br/><br/>注：当 GrantTypes 包含 refresh_token 时，refreshTokenValiditySeconds 为必传参数|
|**multiTenant**|Boolean|False|false|是否为多租户应用<br/>false：该应用仅支持当前创建应用的租户访问，其他京东云租户无法访问<br/>true：该应用支持其他京东云租户访问，但当前创建应用的租户不能访问|
|**userType**|String|True| |能访问应用的账号类型，支持以下值：<br/>（1）root：<br/>（2）sub：|
|**contacts**|String|False| |contacts|
|**extension**|String|False| |extension|
|**jwks**|String|False| |jwks|
|**jwksUri**|String|False| |jwksUri|
|**logoUri**|String|False| |logoUri|
|**policyUri**|String|False| |policyUri|
|**clientUri**|String|False| |clientUri|
|**scope**|String|False| |scope|
|**secret**|String|False| |secret|
|**tosUri**|String|False| |tosUri|



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
