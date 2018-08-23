# deleteBucket


## 描述
该操作可删除指定Bucket。删除Bucket前需将其中的所有Object删除。


## 请求方式
DELETE

## 请求地址
https://oss.jdcloud-api.com/v1/regions/{regionId}/buckets/{bucketname}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**bucketname**|String|True|无|bucket名字，例如：test-bucket|
|**regionId**|String|True|无|Region ID，例如：cn-north-1|

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
DELETE /v1/regions/cn-east-2/buckets/openapi-test HTTP/1.1
Accept-Encoding: gzip
Authorization: signatureValue
Content-Type: application/json
User-Agent: JdcloudSdkJava/0.9.2 oss/v1 Google-HTTP-Java-Client/1.22.0 (gzip)
x-jdcloud-nonce: b0ce87ca-e4fa-4879-b6ca-85ff8056dc0a
x-jdcloud-date: 20180822T114015Z
Host: oss.jdcloud-api.com
Connection: Keep-Alive
```

### 响应示例
```
HTTP/1.1 204 No Content
Date: Wed, 22 Aug 2018 11:40:19 GMT
Content-Type: text/xml;charset=UTF-8
Connection: close
x-jdcloud-limit-minute: 1000
x-jdcloud-remaining-minute: 999
Server: JDCloudOSS
x-req-id: 9C4F665D15F1FA0D
x-jss-service: DELETE.bucket
x-jdcloud-request-id: bdvko8r7f7tn13b8npv6aricggquu47j
x-jdcloud-upstream-latency: 545
x-jdcloud-proxy-latency: 37
x-jdcloud-via: jdcloud
```
