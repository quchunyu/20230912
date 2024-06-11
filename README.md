# GitHub

## 关键字查询
xx **awesome**:查该标签下的xx项目

xx **tutorial**:查询xx(python)资料、书籍、文档<br>
xx **sample**:查询对应技术(socket)的代码样本<br>
## GitHub三要素:
### Repository 仓库
仓库是github项目管理存储基本单位
一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库分为**public**，**private**
### Commit 提交:
程序员在整个开发周期，有大量的对代码资源的选代和修改，都可以通过commit的方式进行
记录,便于程序员回溯代码, 即使这些代码被删除
提交便于使用者观察整个工程的开发流程以及设计流程
### Branch 分支:
在仓库中可以包含多个分支，分支才是代码文件的**第一存储单位**，默认的仓库主分支为
master/main不仅可以管理代码存储，便于多人协作开发
### 仓库内容
**Code**，资源存储，代码资源，二进制，项目管理脚本，许可证等等
**issues**，使用时遇到的bug 或 进行提交，等待反馈
**README**，使用markdown语言编写，工程自述文件，开发进度，，版本更新，使用介绍等
等
**LICENSE** 许可证:GPL2.0,3.0.Apahce 2.0，Mit，这些许可证，给使用者最大使用权限>以及最少的限制

# Git
通过git完成与GitHub的交互
git中存在两个版本：正常情况下本地版本比云端版本新

### 1.创建本地仓库

```c
git init
```
出现（master）即为正确
[![git-init.png](https://i.postimg.cc/ncJxwypF/git-init.png)](https://postimg.cc/9zJsDNDK)

[![20240611000244.png](https://i.postimg.cc/QCg23MhX/20240611000244.png)](https://postimg.cc/RJFs14W8)

### 2.查看配置文件

```c
git  config --list
```

[![20240611084051.png](https://i.postimg.cc/kgHhLSKQ/20240611084051.png)](https://postimg.cc/DSqgX8C0)
### 3.修改config配置

```
git config --global user.name 用户名  //添加用户名
git config --global user.email 邮箱号  //添加邮箱号
```

### 4.生成 SSH 密钥

```c
ssh-keygen -t rsa -C 注册邮箱
```
[![20240611083305.png](https://i.postimg.cc/mr0J19rL/20240611083305.png)](https://postimg.cc/3yFnPdpV)
找打密钥生成的位置，添加到github的seetinngs中的SSH key and GPG中的new ssh key中 

[![20240611084001.png](https://i.postimg.cc/jds9ftR7/20240611084001.png)](https://postimg.cc/CdQmTyBh)
### 5.检测是否关联成功

```c
ssh -T git@github.com
```

![image-20240611084053108](C:\Users\12194\AppData\Roaming\Typora\typora-user-images\image-20240611084053108.png)

## 文档/代码上传步骤

### 1.为仓库起别名

```c
git remote add orgin(别名) SSH地址     //为仓库起别名（方便之后使用）
git remote remove origin   //删除地址别名
```

上传的逻辑：分为两个仓库：本地仓库和云端仓库

1.我们需要将写好的内容上传到缓冲区中

2.将缓冲区中的代码提交到本地仓库中那个

3.将本地仓库中的代码根据分支push到云端仓库中，云端仓库的版本也被更新，同本地仓库一致

### 2.将内容上传到缓冲区

```c
git add README.md
```

### 3.将缓冲区中的内容提交到本地仓库中

```c
git commit -m "README" //""中的内容为注释
```

### 4.本地仓库中的内容push到云端

```c
git push origin master
```
[![20240611085707.png](https://i.postimg.cc/0j9t701s/20240611085707.png)](https://postimg.cc/0MHdsmNW)
[![20240611085755.png](https://i.postimg.cc/7YsBTzBF/20240611085755.png)](https://postimg.cc/kBSN02Ps)
### 5.一些其他命令

```c
git status     //查看状态
git rm 文件名      //删除本地及文件及仓库中内容
git restore 文件名    //回复删除的本地文件（rm直接删除的）

```

### 6. git pull

当直接修改github上的代码会导致依赖关系破坏，需要使用git pull --rebase origin master代码

```
git pull --rebase origin master
git rebase --abort   #忽略新版
git rebase --skip    #需略旧版
git rebase --continue    #版本合并
```


# MarkDwon语言

轻量级文本标记语言，将纯文本转换成HTML文档
## 标题修饰符
修饰符与正文之间要有空格

# (一级标题)
## (二级标题)
### (三级标题)
#### （四级标题）

## 换行用\<dr\>表示
*斜体*
**粗体**
***粗斜体***
~~字体~~

## \-\-\-表示分割线
---

## \>表示引用
>aaaaaaaaaaaaaaaaaaa
>>aaaaaaa
>>
>>>aaaaa

## 无序列表
* 西游记
  * 猴子
    * 孙悟空
  * 猪
    * 猪八戒

## 有序列表1.
1. 三国演义
   * 男
      * 宋江
      * 武松
   2. 女

## 表格
姓名|性别|年龄
--|:--:|--:
小王|男|20
小李|男|19
小郑|女|18

## 代码
```c
        #include<stdio.h>
        int main(){
                return 0;
        }
```

```cpp
        #include<iostream>
        int main(){
                return 0;
        }
```
