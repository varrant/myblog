## ip mac直接在控制台输入ip就能显示和拷贝自己的ip地址
### 方法：
#### 把下面代码放到ip文件中，然后把ip文件拷贝到/usr/local/bin目录下，并且给予ip这个文件777权限
```javascript
#! /bin/sh
###快速查看本机IP地址
myip="$(ifconfig | grep 'inet.*netmask.*broadcast')"
lanip="$(echo $myip | awk '{print $2}')"
publicip="$(echo $myip | awk '{print $6}')"
echo '你的局域网IP是: '$lanip
echo '你的外网IP是: '$publicip
echo $lanip | pbcopy
```