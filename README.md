# cos_pics
一批比较安全的妹子图，目前约13000张。

## 注意事项
* 国内请使用jsdelivr.net加速，否则速度很慢。只要在文件的仓库路径前添加`https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/`即可，比如：
  * `cos_index.js` -> `https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@vlatest/cos_index.js`
  * `cos_0011.js` -> `https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/cos_0011.js`
  * `0a16f8a52af7/20140122095237390.jpg` -> `https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/46ec99606114/1496026269124938.jpg`
* 每100张图片有一个索引文件，名为cos_xxxx.js，前端可以用jsonp方式引用，文件名和jsonp中的函数名相同。见如下例程：
  ```js
  function cos_0011 (arr) {
    for (var img of arr) {
      var el = document.createElement('img')
      el.src = 'https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/' + img.path
      document.getElementById('imgContainer').appendChild(el)
    }
  }
  var sc = document.createElement('script')
  sc.type = 'module'
  sc.src = 'https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/cos_0011.js'
  document.getElementsByTagName('head')[0].appendChild(sc)
  ```
* 后端使用则可以删除js源文件前面的`cos_xxxx(`和最后的`)`后作为普通json解析。
* cos_index.js是总目录，包含所有索引文件的名字列表，jsonp用法参考索引文件
* 为了减小图片空间占用，所有图片均为30万像素（约640x480），JPEG压缩质量为75，色度抽样值为4:2:0
