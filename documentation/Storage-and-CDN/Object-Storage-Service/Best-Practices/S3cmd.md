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
