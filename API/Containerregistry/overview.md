# cr


## 简介
容器镜像仓库服务


### 版本
v1


## API
|接口名称|请求方式|功能描述|
|---|---|---|
|**checkRegistryName**|POST|查询指定注册表名称是否已经存在以及是否符合命名规范。</br>|
|**createRegistry**|POST|通过参数创建注册表。</br>|
|**createRepository**|POST|通过参数创建镜像仓库。</br>仓库名称可以分解为多个路径名，每个名称必须至少包含一个小写字母数字，考虑URL规范。</br>支持包含段划线或者下划线进行分割，但不允许点'.'，多个路径名之间通过("/")连接，总长度不超过256个字符，当前只支持二级目录。</br>|
|**describeImages**|GET|返回指定repository中images的元数据，包括image size, image tags和creation date。</br>|
|**describeQuotas**|GET|查询配额|
|**getAuthorizationToken**|POST|<p>申请12小时有效期的令牌。 使用<code>docker</code> CLI push和pull镜像。</p></br><p><code>authorizationToken</code>为每个registry返回一个base64编码的字符串，解码后<code>docker login</code>命令</br>可完成指定registry的鉴权。JCR CLI提供<code>jcr get\-login</code>进行认证处理。</p></br>|
