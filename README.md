# Dingtalk-Grouplive-Likes-Helper
> ***注意***<br>
> *由于钉钉更新修复了之前的点赞BUG, 故现在单次点赞的最大数值为20, 单次点赞数超过20将不会起任何作用*
## 关于本工具
* 基于[Fiddler](https://www.telerik.com/fiddler)制作
* 可修改单次点赞数
* 可开启自动点赞
* 可修改点赞间隔时间
* 已去除禁用点赞
## 使用方法
* **Step 1** : 安装`Fiddler`
* **Step 2** : 开启`HTTPS`
* **Step 3** : 开启`AutoResponder`(注意勾选`Unmatched requests passthrough`)
* **Step 4** : 添加`https://h5.m.taobao.com/tblive/dingtalk/pc-live-v3.html`到`AutoResponder`规则中, 并将其替换为修改后的`pc-live-v3.html`
## 修改方法
用文本编辑器搜索`uploadLikesClick`, 找到如下一段代码
```javascript
function(){t.favorCountCache>0&&(dingtalk.grouplive.uploadLikesClick($,单次点赞数),是否自动点赞)},点赞间隔时间
```
***注意***
* 单次点赞数上限为`20`, 总点赞数上限为`2147483647`
* 当值为`1`时开启自动点赞, 值为`0`时关闭自动点赞
* 点赞间隔时间建议设置为`1`
