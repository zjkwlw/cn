# 错误响应列表

|错误码|说明|HTTP状态码|备注|
|-|-|-|-|
|AccessDenied|Access Denied|403|访问被拒绝|
|AccountProblem|There is a problem with your JSS account that prevents the operation from completing successfully.|403|帐号被冻结，通常是流量超标或者其他原因引起|
|AccessKeyLimited|The access key policy that prevents the operation from completing successfully.|403|要创建的 Bucket 已存在 ，Bucket名称全局唯一，请重新选择|
|BucketAlreadyExists|The requested bucket name is not available. The bucket namespace is shared by all users of the system. Please select a different name and try again.|409|要创建的Bucket已存在，Bucket名称全局唯一，请重新选择|
|InvalidLocationConstraint|The specified location constraint is not valid.|400|您所选择的区域不存在|
|BucketAlreadyOwnedByYou|Your previous request to create the named bucket succeeded and you already own it.|409|您已创建相同名称的bucket|
|InvalidBucketName|The specified bucket is not valid.|400|要创建的Bucket名称不合法|
|InvalidObjectKey|The specified object key is not valid.|400|指定的Object key名称不合法|
|EntityTooLarge|Your proposed upload exceeds the maximum allowed object size.|400|上传的数据大小超过了限制，目前最大支持单个文件大小为5G|
|EntityTooSmall|Your proposed upload is smaller than the minimum allowed object size.|400| |
|MissingContentLength|You must provide the Content-Length HTTP header.|400|在HTTP Header 中缺少Content-Length|
|BucketNotEmpty|The bucket you tried to delete is not empty.|409|需要删除的bucket不为空|
|BucketNotEmpty|The bucket you tried to delete has some muti uploads didn't delete.|409|需要删除的bucket有尚未删除的上传分片|
|BucketNotEmpty|The bucket you tried to delete has acl didn't delete.|409|需要删除的bucket有没有删除的ACL|
|BadDigest|The Content-MD5 you specified did not match what we received.|400|提供的Content-MD5值与服务端计算的不匹配|
|RequestTimeTooSkewed|The difference between the request time and the server's time is too large.|400|请求的时间戳与服务器本地时间差距过大，被拒绝|
|InvalidPart|One or more of the specified parts could not be found. The part might not have been uploaded, or the specified entity tag might not have matched the part's entity tag.|400|Complete Multipart Upload时，HTTP请求中的Part在云存储中找不到，可能这些Part没有被上传|
|TooManyParts|Part number must less than 10000.|400| |
|BadContentLength|Object content length your specified did not match what we received.|400| |
|ConnectionLost|Your socket connection to the server may be lost while we receiving data.|400| |
|RequestTimeout|Your socket connection to the server was not read from or written to within the timeout period.|400| |
|SlowDown|Please reduce your request rate.|400| |
|AccessKeyDenied|the user already has keys.|400| |
|NoSuchFile|The file doesn't exist,please upload the file again!|400| |
|DecryptError|Decrypt the file error, the file encrypt by bad way!|400| |
|ExpiredToken|The provided token has expired.|400| |
|InvalidRange|The requested range cannot be satisfied.|416| |
|KeyTooLong|Your key is too long.|400| |
|NoSuchBucket|The specified bucket does not exist.|404| |
|NoSuchKey|The specified key does not exist.|404| |
|InvalidPartOrder|The list of parts was not in ascending order.Parts list must specified in order by part number.|400| |
|PreconditionFailed|At least one of the preconditions you specified did not hold.|412| |
|MalformedPOSTRequest|The body of your POST request is not well-formed multipart/form-data.|400| |
|MalformedPolicy|The policy of your request is not well-formed.|400| |
|IncorrectNumberOfFilesInPostRequest|POST requires exactly one file upload per request.|400| |
|UserKeyMustBeSpecified|The bucket POST must contain the specified field name. If it is specified, check the order of the fields.|400| |
|TooManyBuckets|You have attempted to create more buckets than allowed.|400| |
|TooManyMultipartUploads|You have attempted to initiate more multipart uploads than allowed.|400| |
|InternalError|We encountered an internal error. Please try again.|500| |
|InvalidToken|The provided token is malformed or otherwise invalid.|403| |
|BadRequest|Bad Request|400| |
|InvalidPolicyDocument|The content of the form does not meet the conditions specified in the policy document.|400| |
|InvalidURI|Couldn't parse the specified URI.|400| |
|SignatureDoesNotMatch|The request signature we calculated does not match the signature you provided.|403| |
|InvalidArgument|InvalidArgument|400| |
|MethodNotAllowed|The specified method is not allowed against this resource.|405| |
|NotSuchBucketPolicy|The specified bucket does not have a bucket policy.|404| |
|InvalidPayer|All access to this object has been disabled.|403| |
|MalformedJson|The JSON you provided was not well-formed or did not validate against our published schema.|400|
|NoSuchUpload|The specified multipart upload does not exist. The upload ID might be invalid, or the multipart upload might have been aborted or completed.|404| |
|MissingSecurityHeader|Your request was missing a required header.|400| |
|InvalidAccessKeyId|The Access Key Id you provided does  not exist in our records.|403| |
|InvalidCallback|upload success but callback failed.|567| |
|NoSuchPattern|The specified pattern does not exist.|404| |
|InvalidTargetObjectKey|The specified target object key has already exists.|400| |
|BucketHasPictureStyle|The bucket you tried to delete has PictureStyle didn't delete.|409| |
|IncompleteBody|You did not provide the number of bytes specified by the Content-Length HTTP header.|400|
