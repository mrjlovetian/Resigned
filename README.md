## 查看描述文件信息: $security cms -D -i 描述文件路径

### 查看APP的签名信息
$codesign -vv -d APP路径

### 查看本机所有证书
$security find-identity -v -p codesigning

### 查看可执行文件的加密信息!
$otool -l WeChat | grep crypt

### 签名
$codesign -fs "证书" 需要签名的文件



### 重签名:
1.干掉插件Plugins文件夹里面的内容!
2.Watch 直接干掉!
3.对 Frameworks 进行签名!
4.给可执行文件执行权限! chmod +x WeChat
5.拷贝描述文件
6.修改info.plist 的Bundle ID!
7.生成plist的权限文件
8.签名整个APP!
	$codesign -fs "iPhone Developer: WenHan Li (6ZBE4C573L)"  --no-strict --entitlements=en.plist WeChat.app

9.打包其实就是一个zip
$zip -ry WeChat.ipa Payload

