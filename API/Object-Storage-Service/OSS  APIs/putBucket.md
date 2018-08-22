# putBucket


## 描述
该操作可实现创建一个Bucket

## 请求方式
PUT

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
|**409**|The requested bucket name is not available. The bucket namespace is shared by all users of the system.<br>Please select a different name and try again.|

## 示例
### 请求示例
```
PUT /v1/regions/cn-east-2/buckets/openapi-test HTTP/1.1
Accept-Encoding: gzip
Authorization: signatureValue
Content-Type: application/json
User-Agent: JdcloudSdkJava/0.9.2 oss/v1 Google-HTTP-Java-Client/1.22.0 (gzip)
x-jdcloud-nonce: f8216ad0-a4c3-4327-8475-bf2317f6b9f9
x-jdcloud-date: 20180822T103126Z
Content-Length: 51
Host: oss.jdcloud-api.com
Connection: Keep-Alive

{"regionId":"cn-east-2","bucketname":"openapi-test"}
```
### 响应示例
```
HTTP/1.1 201 Created
Date: Wed, 22 Aug 2018 10:31:30 GMT
Content-Type: text/plain; charset=UTF-8
Content-Length: 0
Connection: close
x-jdcloud-limit-minute: 1000
x-jdcloud-remaining-minute: 999
Server: JDCloudOSS
x-req-id: BFE8338F9D1CA6E6
x-jss-service: PUT.bucket
x-jdcloud-request-id: bdvjo0k5g1wvt87g0a1cd9ws52h5o41i
x-jdcloud-upstream-latency: 222
x-jdcloud-proxy-latency: 158
x-jdcloud-via: jdcloud
```
