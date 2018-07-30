# 使用S3cmd管理京东云OSS

## 简介

S3cmd是一个免费的命令行工具客户端，用于在Amazon S3和其他使用S3协议的云存储服务提供商（如京东云OSS）上传，检索和管理数据。它适合熟悉命令行程序的高级用户。它也是批处理脚本和S3自动备份的理想选择，由cron等触发。

使用场景：API级别的开发、调试。

## 环境要求

S3cmd环境要求：S3cmd在Linux（Fedora，RedHat，SuSe，Ubuntu，Debian等）和Apple MAC上运行。需要Python 2.6或更高版本。S3cmd version 2也与Python 3.x兼容。

Python版本查看：Linux shell环境下输入python并回车，来查看Python的版本。如下所示：
```
Python 2.7.12 (default, Dec  4 2017, 14:50:18) 
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
以上说明python安装成功。如果没有安装Python，可以从[python官网](https://www.python.org/?spm=a2c4g.11186623.2.4.YmMQuB)获取Python的安装包。网站有详细的安装说明来指导您如何安装和使用Python。

## 安装使用

**下载S3cmd**
```
git clone https://github.com/s3tools/s3cmd.git
```
**源码修改**

使用V4签名，不使用V2签名，从https://github.com/s3tools/s3cmd.git下载后进入以下目录。

文件目录：s3cmd/S3/S3.py，其中第254行修改为：self.endpoint_requires_signature_v4 = True

S3CMD修改.png

**S3cmd安装**
```
sudo cp -f s3cmd/ /usr/local/
sudo ln -s /usr/local/s3cmd/s3cmd /usr/bin/s3cmd
```

**配置文件**

配置文件为~/.s3cfg，下面是使用的配置文件的内容：
```
[default]
access_key = [you access key]
access_token = 
add_encoding_exts = 
add_headers = 
bucket_location = cn
ca_certs_file = 
cache_file = 
check_ssl_certificate = True
check_ssl_hostname = True
cloudfront_host = cloudfront.amazonaws.com
default_mime_type = binary/octet-stream
delay_updates = False
delete_after = False
delete_after_fetch = False
delete_removed = False
dry_run = False
enable_multipart = True
encrypt = False
expiry_date = 
expiry_days = 
expiry_prefix = 
follow_symlinks = False
force = False
get_continue = False
gpg_command = /usr/bin/gpg
gpg_decrypt = %(gpg_command)s -d --verbose --no-use-agent --batch --yes --passphrase-fd %(passphrase_fd)s -o %(output_file)s %(input_file)s
gpg_encrypt = %(gpg_command)s -c --verbose --no-use-agent --batch --yes --passphrase-fd %(passphrase_fd)s -o %(output_file)s %(input_file)s
gpg_passphrase = 
guess_mime_type = True
host_base = s3.cn-north-1.jcloudcs.com
host_bucket = %(bucket)s.s3.cn-north-1.jcloudcs.com
human_readable_sizes = False
invalidate_default_index_on_cf = False
invalidate_default_index_root_on_cf = True
invalidate_on_cf = False
kms_key = 
limit = -1
limitrate = 0
list_md5 = False
log_target_prefix = /home/eric/jcloud/s3.log
long_listing = False
max_delete = -1
mime_type = 
multipart_chunk_size_mb = 15
multipart_max_chunks = 10000
preserve_attrs = True
progress_meter = True
proxy_host = 
proxy_port = 0
put_continue = False
recursive = False
recv_chunk = 65536
reduced_redundancy = False
requester_pays = False
restore_days = 1
restore_priority = Standard
secret_key = [you secret key]
send_chunk = 65536
server_side_encryption = False
signature_v2 = False
simpledb_host = sdb.amazonaws.com
skip_existing = False
socket_timeout = 300
stats = False
stop_on_error = False
storage_class = 
urlencoding_mode = normal
use_http_expect = False
use_https = False
use_mime_magic = True
verbosity = WARNING
website_endpoint = http://%(bucket)s.s3-website-%(location)s.amazonaws.com/
website_error = 
website_index = index.html
```

**验证S3cmd是否可用**

Linux shell环境下输入s3cmd并回车，如下所示即可使用：

检验S3cmd命令是否可用.png

如下以Make bucket为例，测试S3cmd是否可用：

S3命令测试.png

## 支持功能

以下是目前S3cmd所支持京东云OSS的命令：

Commands：

<table border=0 cellpadding=0 cellspacing=0 width=318 style='border-collapse:
 collapse;table-layout:fixed;width:500pt'>
 <col width=69 style='width:52pt'>
 <col width=249 style='mso-width-source:userset;mso-width-alt:7978;width:187pt'>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl65 width=69 style='height:14.5pt;width:52pt'>功能类型</td>
  <td class=xl66 width=249 style='width:187pt'>功能命令</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td rowspan=24 height=456 class=xl71 width=69 style='border-bottom:1.0pt solid black;
  height:342.0pt;border-top:none;width:52pt'>管理Bucket</td>
  <td class=xl67 width=249 style='width:187pt'>Make bucket</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd mb
  s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Remove
  bucket</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd rb
  s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>List
  objects or buckets</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd ls
  [s3://BUCKET[/PREFIX]]</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Disk
  usage by buckets</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd du
  [s3://BUCKET[/PREFIX]]</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Modify
  Access control list for Bucket or Files</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  setacl s3://BUCKET[/OBJECT]</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Modify
  Bucket Policy</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  setpolicy FILE s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Delete
  Bucket Policy</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  delpolicy s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Modify
  Bucket CORS</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  setcors FILE s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Delete
  Bucket CORS</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  delcors s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Create
  Website from bucket</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  ws-create s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Delete
  Website</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  ws-delete s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Info
  about Website</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  ws-info s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td rowspan=14 height=266 class=xl74 width=69 style='border-bottom:1.0pt solid black;
  height:199.5pt;border-top:none;width:52pt'>管理Object</td>
  <td class=xl67 width=249 style='width:187pt'>Put file into bucket</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl69 width=249 style='height:14.5pt;width:187pt'>s3cmd
  put FILE [FILE...]s3://BUCKET[/PREFIX]</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Get file
  from bucket</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  get s3://BUCKET/OBJECT LOCAL_FILE</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Delete
  file from bucket</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  del s3://BUCKET/OBJECT</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Delete
  file from bucket (alias for del)</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd rm
  s3://BUCKET/OBJECT</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Show
  multipart uploads</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  multipart s3://BUCKET [Id]</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Abort a
  multipart upload</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  abortmp s3://BUCKET/OBJECT Id</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>List
  parts of a multipart upload</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  listmp s3://BUCKET/OBJECT Id</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td rowspan=10 height=253 class=xl74 width=69 style='border-bottom:1.0pt solid black;
  height:189.5pt;border-top:none;width:52pt'>其他功能</td>
  <td class=xl67 width=249 style='width:187pt'>Sign arbitrary string using the
  secret &nbsp; key</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl68 width=249 style='height:14.5pt;width:187pt'>s3cmd
  sign STRING-TO-SIGN</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>Get
  various information about Buckets or &nbsp; Files</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td height=19 class=xl67 width=249 style='height:14.0pt;width:187pt'>s3cmd
  info s3://BUCKET[/OBJECT] 注：不支持显示bucket的信息，显示object的信息不完全</td>
 </tr>
 <tr height=46 style='height:34.5pt'>
  <td height=46 class=xl67 width=249 style='height:34.5pt;width:187pt'>Synchronize
  a directory tree to S3 (checks files freshness using size and md5 checksum,
  unless overridden by options, see below)</td>
 </tr>
 <tr height=31 style='height:23.0pt'>
  <td height=31 class=xl70 width=249 style='height:23.0pt;width:187pt'>s3cmd
  sync LOCAL_DIR s3://BUCKET[/PREFIX] or s3://BUCKET[/PREFIX] LOCAL_DIR 注：不会自动同步，需要自己输入这条命令来同步一个目录。</td>
 </tr>
 <tr height=31 style='height:23.0pt'>
  <td height=31 class=xl70 width=249 style='height:23.0pt;width:187pt'>Sign an
  S3 URL to provide limited public access with expiry s3cmd signurl
  &nbsp;&nbsp;</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl69 width=249 style='height:14.5pt;width:187pt'>s3://BUCKET/OBJECT
  &lt;expiry_epoch|+expiry_offset&gt;</td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=69 style='width:52pt'></td>
  <td width=249 style='width:187pt'></td>
 </tr>
 <![endif]>
</table>
