# listBuckets


## 描述
列出当前用户的所有bucket。


## 请求方式
GET

## 请求地址
https://oss.jdcloud-api.com/v1/regions/{regionId}/buckets

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True||Region ID，例如：cn-north-1|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String||
|**result**|[Result](##Result)||


### <a name="Result">Result</a>
|名称|类型|描述|
|---|---|---| 
|**buckets**|[Bucket[]](##Bucket)||
|**owner**|[User](##User)||
### <a name="Bucket">Bucket</a>
|名称|类型|描述|
|---|---|---|
|**creationDate**|String||
|**name**|String||
### <a name="User">User</a>
|名称|类型|描述|
|---|---|---|
|**displayName**|String||
|**id**|String||

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Invalid Argument|
|**403**|Access Denied|

## 示例
### 请求示例
```
GET /v1/regions/cn-north-1/buckets HTTP/1.1
Accept-Encoding: gzip
Authorization: signatureValue
Content-Type: application/json
User-Agent: JdcloudSdkJava/0.9.2 oss/v1 Google-HTTP-Java-Client/1.22.0 (gzip)
x-jdcloud-nonce: ca69f7ca-2bdc-4a86-8af0-4830b92f7976
x-jdcloud-date: 20180822T074805Z
Host: vm.jdcloud-api.com
Connection: Keep-Alive 
```
### 返回示例
```
HTTP/1.1 200 OK
Date: Wed, 22 Aug 2018 07:48:09 GMT
Content-Type: text/xml;charset=UTF-8
Transfer-Encoding: chunked
Connection: close
x-jdcloud-limit-minute: 1000
x-jdcloud-remaining-minute: 999
Server: JDCloudOSS
Vary: Accept-Encoding
x-req-id: 8E8E4E8E21F73CB0
x-jss-service: GET.service
x-jdcloud-request-id: bdvhaecj8hccq05p7sdc40oqbp7dgan1
Content-Encoding: gzip
x-jdcloud-upstream-latency: 20
x-jdcloud-proxy-latency: 209
x-jdcloud-via: jdcloud

{"requestId":"8E8E4E8E21F73CB0","result":{"owner":{"id":"243035305301","displayName":"jcloudiaas4"},"buckets":[{"name":"jss-test","creationDate":"2017-07-18T10:52:21.000Z"}]}}
```
