## 问题
一些可在浏览器中打开的文件，如pdf，浏览器会直接打开它，而不是下载。

## a标签的download属性
在a标签上添加download属性，如：

```html
<a href="test.pdf" download></a>
```
测试后发现Chrome和Firefox会直接下载，而在IE和Edge中仍然会打开pdf。

## Content-Disposition响应头
在文件请求的响应头中添加：Content-Disposition:attachment，发现在Chrome\Firefox\IE\Edge中均为直接下载文件

以下为node express测试代码

```javascript
//下载
//如，访问http://localhost:3942/download/test.pdf会下载test.pdf
app.use('/download', express.static('downloadFiles', {
    setHeaders: function (res, path, stat) {
        res.set({
            'Content-Disposition': 'attachment',
        })
    }
}))
//打开
//如，访问http://localhost:3942/browse/test.pdf会在浏览器中打开test.pdf
app.use('/browse', express.static('downloadFiles', {
    setHeaders: function (res, path, stat) {
        res.set({
            'Content-Disposition': 'inline',
        })
    }
}))
```
