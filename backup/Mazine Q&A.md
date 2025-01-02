# 注意事项

## 不支持上传带#命名的图片!
名字不容易解码，也无法转码。
测试了非常复杂的命名都可以，其他字符应该没问题。带空格的，日文，简中、繁中，中文符号的.....

`JUL-983 【三浦歩美】永遠に終わらない、 有码-poster.jpg`

但将这个命名的照片收藏后，在收藏页面中命名的转码就有点小bug,但管理页面中的命名是正确的，URL也没有错。
不想修正这个bug，就当这是我纯粹技术不足吧，要解决这问题得花很长时间，不值得。

_题外话，这车牌还行。_

##  图床登录页面更改背景
 图床仅支持登录页面更改背景 ！
应用页面中不能修改自定义背景，从规划开始就妹打算搞，以后也没有计划打算修改。
 **本来就花眼，还自定义背景我怕瞎！**

登录页面修改路径/app/login/page.tsx 第16 行

 ### 自定义背景 
` const [bgImage, setBgImage] = useState<string | null>('https://onlyfan.com/1734736654213-8wrxdb.png')`
 ### 默认背景 
`const [bgImage, setBgImage] = useState<string | null>('null')`


## 图片压缩率默认0.75
图片压缩率修改路径/app/home/page.tsx 第155行
```
        if (compress) {
          try {
            const options = {
              maxSizeMB: 1,    //控制文件容量大小
              maxWidthOrHeight: 1920,   //控制图片尺寸大小
              useWebWorker: true,
              quality: 0.75   //这里控制压缩率
            }

```

## 如何预览已上传图片？
在上传页面的总预览模块中直接点击图片卡片即可预览！
在管理页面和收藏页面中，点击图片卡片是**勾选**的意思，若按住**ctrl**并点击图片卡片打开**图片预览模式**（如下图）。


![](https://img.erpweb.eu.org/imgs/2025/01/39b9adab30453e2e.png)

**图片预览模式**

![](https://img.erpweb.eu.org/imgs/2025/01/8c96422b69c47431.png)

## 收藏和取消收藏
管理页面只负责收藏和删除功能，通过点选图片进行勾选批处理。不能取消收藏！

![](https://img.erpweb.eu.org/imgs/2025/01/be6e2ca3a915c089.png)

收藏页面只支持取消收藏，通过点选图片进行勾选批处理。不能进行删除或重新收藏！

![](https://img.erpweb.eu.org/imgs/2025/01/2ef14a022287f56e.png)

上传页面支持收藏和取消收藏！
### _这个不是技术问题，这个是逻辑问题，避免误操作。_


## TOP键放在顶栏右上角主题切换的右边

![](https://img.erpweb.eu.org/imgs/2025/01/9d391ffed47854d9.png)
