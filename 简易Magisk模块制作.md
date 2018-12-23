# 简易Magisk模块制作

## Magisk简单说明

Magisk框架的左右简单来说就是文件替换过增减
比如要替换体统某文件，把你需要的文件搞成个模块
然后Magisk框架挂着让它生效
实际上并没有改动系统但达成了一样效果
还能方便开关
比直接修改系统更安全方便

## 简易制作过程

以用手机制作替换hosts文件的模块为例

### 准备部分

* 下载模块模板

  [Magisk作者的原始模板](https://github.com/topjohnwu/magisk-module-template)
  
  [汉化的模板](https://github.com/Magisk-Modules-Repo-CN/magisk-module-template) 新人推荐
  
  下载方式：Clone or download - Download Zip
  
* 准备一个可用Magisk模块

  随便一个就行。比如冰箱的权限模块。

* [MT管理器2.0](https://www.coolapk.com/apk/bin.mt.plus)装一个。不用会员的。

* 准备好你要替换的文件

  比如修改版APP，这里是以一个网上找的去广告hosts文件为例
 
* 确认你要替换的文件在系统中的完整路径

   比如hosts文件路径为/system/etc/hosts
   
### 操作

运行MT管理器

1.首先
  * 打开冰箱模块，以及模块模板
  * 把冰箱模块内的文件和文件夹全删除，把模板内的文件夹与文件复制一份过去

2.然后在“冰箱模块”内按照替换文件的目录一一创建文件夹

  并把替换文件复制进去
  
  * 在这里hosts文件在/system/etc目录下
  
    就是在system文件夹创建一个etc文件夹，并把准备好的hosts文件复制进etc里面
   
3.点击“冰箱模块”内config.sh，编辑
  
  按里面文本提示，在对应位置加一行/system/etc/hosts（表示把文件替换到这里）
    
  保存退出。
  
  * 比如在这里就是REPLACE="后回车加一行，填写/system/etc/hosts
    
    保存退出
    
    >> 注意不能只写/system/etc。它代表把目录下文件替换为hosts
    
       假设你想更换一个app，安装目录下只有一个apk文件，那么只写安装目录就行
       
       但是/system/etc文件夹中有很多文件。你如果这么写会无法开机。别问我怎么知道的。
  
4.点击module.prop编辑【很随意，进行命名等】

  对应项目如下
  
  * id=ccc             只能是字母数字
  * name=              模块模板 命名。自由。
  * version=v1         版本号。自由。
  * versionCode=1      随意数字。
  * author=topjohnwu   作者名字。自由。
  * description=描述   自由
  * minMagisk=17000    模板版本号，只是检测一下，不动
  
5.退出，把“冰箱模块”按照自己喜好命名。
  
  这个模块就诞生了。可以用了。

### 稍微进阶
   想替换多个文件？
   把要换的依样画葫芦一一塞进去
   然后去config.sh按照模板样式一行行添加对应目录
   就行了。

### 尝试是否可用之前装个MM管理器防止翻车
### 尝试是否可用之前装个MM管理器防止翻车
### 尝试是否可用之前装个MM管理器防止翻车

## 完毕
