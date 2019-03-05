# 测试服使用规范

目前测试服配置了两个域名供大家使用，一个是头条的域名：`testshfe.eastday.com`，一个是猫扑的域名：`testshfe.mop.com`，配置此测试服的目的主要是方便前端和产品、设计进行项目测试、验收和跟踪，减少沟通成本。配置两个域名的目的是方便广告测试（有些广告认域名的），请大家按照以下规则提交代码，代码提交后即可通过对应的域名目录访问到。

## hosts 绑定

`123.59.141.96 testshfe.eastday.com testshfe.mop.com`

## testshfe.eastday.com

头条相关的项目请使用此域名。

## svn 账号密码

- 账号：姓名全拼（如：lizhigao）
- 密码：'shfe\_'+姓名首字母（如：shfe_lzg）

### svn 地址

`svn://123.59.141.96/eastday`（对应的访问 url 地址目录为：`http://testshfe.eastday.com/eastday/`）

### 使用说明

每人在`svn://123.59.141.96/eastday`下建一个用自己名字命名的文件夹（如：`lizhigao`），将要测试的代码放到自己文件夹下提交。
如果成功绑定 hosts，即可通过以下方式访问：`http://testshfe.eastday.com/eastday/姓名全拼/项目名/index.html` （如：`http://testshfe.eastday.com/eastday/lizhigao/testproject/index.html`）

## testshfe.mop.com

猫扑相关的项目请使用此域名。

### svn 地址

`svn://123.59.141.96/mop`（对应的访问 url 地址目录为：`http://testshfe.mop.com/mop/`）

### 使用说明

每人在`svn://123.59.141.96/mop`下建一个用自己名字命名的文件夹（如：`lizhigao`），将要测试的代码放到自己文件夹下提交。
如果成功绑定 hosts，即可通过以下方式访问：`http://testshfe.mop.com/mop/姓名全拼/项目名/index.html` （如：`http://testshfe.mop.com/mop/lizhigao/testproject/index.html`）

## 文件上传简单规范【请务必遵守】

- 只允许更新自己目录下的代码；
- 不要上传无用的文件或文件夹；
- 暂时还没做权限限制，请大家不要随意修改、删除他人代码；
- 禁止上传 psd 设计稿；
- 太大的文件、文件夹请三思后再考虑是否要上传。

## 问题

- svn 安装使用问题请自行 Google、百度解决；实在解决不了请找同事或者钉钉、电话联系李志高；
- 如发现账号密码无法登录，钉钉或电话联系李志高添加修改。

## 注意

提交的代码一定是在已自己姓名命名的目录下，不允许提交到其他目录。

## Links

- http://testshfe.eastday.com/eastday/index.html
- http://testshfe.mop.com/mop/index.html
