
# OTA Test 说明

手头上没有 https 地址，借 github 用用


## 说明

主要就是编写一个plist文件，然后做一个链接指向这个plist文件，plist文件必须放在 https 下，借用了 github ，放在

https://raw.githubusercontent.com/MistChen/OTARelease/master/OTATestForKent/OTATestForKent.plist

这个plist文件用来描述相关参数，主要有以下几个：

* `bundle-identifier` : app的id，随便命名，plist 文件中的名字和app定义中名字必须一致，这个这个demo中用的是 `MistChen.OTATest`
	
* `software-package/url` : 打好的ipa包的地址，随便放，能访问到就可以了，可以是 http，这个demo中仍然厚颜无耻的借用了github 
	https://github.com/MistChen/OTARelease/raw/master/OTATestForKent/OTATest.ipa
	
* `title` : 点击安装的时候，给用户的提示，这个demo用的是 `Kent你看看`
	
* `display-image/url` 和 `full-size-image/url` : 这两个是app 在安装的时候，显示的图标，和app可以完全没关系，这个demo 中用的是 
	http://a5.mzstatic.com/us/r30/Purple69/v4/32/5d/e8/325de896-cf36-1b74-19c8-8ebfc86cc20b/icon175x175.png


##下载

下载链接被 markdown 和 github 合伙和谐掉了，移步到

[这个页面下载](http://7xnw7w.com1.z0.glb.clouddn.com/index.html)

下载链接需要实用 `itms-services` 协议，具体是 `itms-services://?action=download-manifest&url=`，url 后面接上 plist 的地址就ok了，你可以看看这页的源代码

另外的几个相关点是：

* 必须使用 ios 设备上的浏览器打开，是不是 safari 无所谓
* ios9.0之后，必须在 `设置 -> 通用 -> 描述文件` 中选择对应的证书，并选择*信任*，才能正常打开App
* 可以写一个 html，使用 js 脚本自动跳转到这个 `itms-services` 链接，就可以做成二维码，扫描之后访问那个自动跳转的页面，就可以实现扫描二维码下载了

