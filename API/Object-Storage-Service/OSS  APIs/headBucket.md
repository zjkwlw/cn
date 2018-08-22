# headBucket


## 描述
此操作用于确定指定Bucket是否存在。


## 请求方式
HEAD

## 请求地址
https://oss.jdcloud-api.com/v1/regions/{regionId}/buckets/{bucketname}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**bucketname**|String|True||bucket名字，例如：test-bucket|
|**regionId**|String|True||Region ID，例如：cn-north-1|

## 请求参数
无

## 返回参数
无

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Invalid Argument|
|**403**|Access Denied|
|**404**|The specified bucket does not exist.|

## 示例
### 请求示例
```
HEAD /v1/regions/cn-east-2/buckets/openapi-test HTTP/1.1
Accept-Encoding: gzip
Authorization: JDCLOUD2-HMAC-SHA256 Credential=59E6DC72927457BDEBF36A56EE616B07/20180822/cn-east-2/oss/jdcloud2_request, SignedHeaders=content-type;host;x-jdcloud-date;x-jdcloud-nonce, Signature=df342d16c4554a834ae383aab9e530eb97a9f675e01ec6635826b1f2dbfadff9
Content-Type: application/json
User-Agent: JdcloudSdkJava/0.9.2 oss/v1 Google-HTTP-Java-Client/1.22.0 (gzip)
x-jdcloud-nonce: ebc08611-c700-45cb-b830-c7706c17b933
x-jdcloud-date: 20180822T112858Z
Host: oss.jdcloud-api.com
Connection: Keep-Alive
```

### 响应示例
```
HTTP/1.1 200 OK
Date: Wed, 22 Aug 2018 11:29:02 GMT
Content-Type: text/plain; charset=UTF-8
Content-Length: 0
Connection: close
x-jdcloud-limit-minute: 1000
x-jdcloud-remaining-minute: 999
Server: JDCloudOSS
x-req-id: 85B2FF17C1F58523
x-jss-service: GET.headBucket
x-jdcloud-request-id: bdvkhwmshop93bod0ojqgca2pkj067ph
x-jdcloud-upstream-latency: 76
x-jdcloud-proxy-latency: 28
x-jdcloud-via: jdcloud
```
