# GitHub配置过程
##注册GitHub账号
请移步：
```
https://github.com
```
## 下载Git
请移步：
```
https://git-scm.com/
```
## 安装Git
请移步：
```
https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000
```
## 配置Git环境变量
打开系统环境变量设置，找到Path，添加 ‘~/Git/cmd’。

## GitHub账户添加SSH key
点击头像选择“Settings”，在侧边选项卡中选择“SSH and GPG keys”。title可以任意填，仅表示你的密钥名称。

### 本地生成ssh key
```
git config --global user.name 'username'
git config --global user.email 'YouEmail.com'
```
–global这个参数，表示这台机器上的所有Git仓库都会使用这个配置，也可以指定仓库用不同的用户名和邮箱。

```
ssh-keygen -t rsa -C 'YouEmail.com'
```
本地生成密钥文件，找到生成路径下的“id_rsa.pub”文件，用记事本或编辑器打开，copy密钥到GitHub的SSH and GPG keys中并Save。

## 上传本地文件到GitHub
首先在GitHub创建一个Repositories，点击头像，选择“Your Repositories”，new一个新的仓库。选择私有或者公有仓库，创建以后点击你的仓库，在仓库的右上角找到“Clone or download”点击，点击“Use SSH”，然后复制仓库地址。

### 本地创建一个仓库
```
mkdir YouRepositoriesName
```
### 进入本地仓库
```
cd YouRepositoriesName
```
### 初始化
```
git init
```
### 将文件添加到远程仓库
```
//本地README.md文件添加到远程仓库
git add README.md

//不但可以跟单一文件，还可以跟通配符，更可以跟目录。一个点就把当前目录下所有未追踪的文件全部add了，注意空格
git add .
```
### 添加注释
```
git commit -m “注释”
```
### 本地关联远程仓库
```
git remote add origin git@github.com:username/YouRepositoriesName.git
```
### 推送到远程仓库
把本地库的所有内容推送到远程库上（第一次需要加-u，后面就不用加了）。
```
git push -u origin master
```

### 更新本地文件到远程仓库
步骤分别为添加、提交、推送。
```
git add <filename>
git commit -m "代码提交信息"
git push origin master
```