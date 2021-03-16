# 足迹地图效果展示

**足迹地图可以展示你过去到访过的地方，以及到访地点的介绍与图片记录**，同时不同地标的半径大小表示了访问该地点的频率高低，如下图所示：

![我的足迹地图](https://sunyunzeng.com/%E5%8D%9A%E5%AE%A2%E4%B8%AD%E6%B7%BB%E5%8A%A0%E8%B6%B3%E8%BF%B9%E5%9C%B0%E5%9B%BE/%E5%9B%BE1.png)

其中每个足迹图标都可以点击，点击会弹出左边的介绍栏及对应的介绍文字与图片。**图片点击可以放大显示**，如下图所示：

![图片放大查看](https://sunyunzeng.com/%E5%8D%9A%E5%AE%A2%E4%B8%AD%E6%B7%BB%E5%8A%A0%E8%B6%B3%E8%BF%B9%E5%9C%B0%E5%9B%BE/%E5%9B%BE2.png)

# 足迹地图使用方式

## 克隆足迹地图项目

**首先，将足迹地图克隆到本地。**

```
git clone https://github.com/SUNYunZeng/FootprintMap.git
```

会得到如下所示的目录结构：


```
FootprintMap
├─ CNAME
├─ css
│  ├─ index.css
│  └─ jquery-jvectormap-2.0.5.css
├─ data
│  └─ config.json
├─ index.html
├─ js
│  ├─ index.js
│  ├─ jquery-1.9.1.min.js
│  ├─ jquery-jvectormap-2.0.5.min.js
│  └─ jquery-jvectormap-cn-merc-en.js
└─ README.md
```

## 配置你的足迹数据

**其中 /data/config.json 为配置数据，在里面可以配置你的足迹数据**，结构如下：

```javascript
[
    {
        "latLng": [36.44852263442782, 118.73921200195313],
        "name": "青州",
        "desc": "我的家乡，山东东方——青州，国家著名旅游城市。\n旅游景点包括云门山、仰天山、驼山、范公亭、青州博物馆、宋城、古街等等。\n著名美食包括弥河银瓜、老槐树煎包、柿饼、马蹄子烧饼等等。",
        "photos":[
            "http://m.qpic.cn/psc?/V115oyNl11FAq7/ETWql2gUF22pNmiMBc.OAZ37OxTay*sinik.eOjVri2aewXK1ZXizNGpMabk*In6gs0SEGmIh82UkaewyV8YgWsu29ZdAYjwW0wjuMdOkzw!/b&bo=VQOAAgAAAAAFF.A!&rf=viewer_4",
            "http://m.qpic.cn/psc?/V115oyNl11FAq7/ETWql2gUF22pNmiMBc.OAQ0A4hJ0OmPEDYmJjUFJKI2t*ynCY41qGPAI.NMZlbUTh6NeqmgL7UuGmHcPH33ZKUpdGUvyUtlsxeRoKQRaaRk!/b&bo=ngL3AQAAAAAFF14!&rf=viewer_4",
            "http://m.qpic.cn/psc?/V115oyNl11FAq7/ETWql2gUF22pNmiMBc.OARYef.ZynHj7VLc8N**aHzaQkp4U5oJI4Saa3W68M7O8ynmpV.j*l1JOYoOcYI*WO7r7NotbsyncY3NuLst7vwM!/b&bo=ngL2AQAAAAAFF18!&rf=viewer_4"
        ],
        "freq": 10
    },
    ...
]
```

- **latLng：** 为足迹的经纬度，可以通过 https://jingweidu.bmcx.com/ 查询得到
- **name：** 足迹地点的名称
- **desc**：足迹地点的描述， \n 为换行符
- **photos**：足迹地点的照片链接，为一组图片 url 数据
- **freq**：足迹地点的到访次数，范围为 [1, 10]

## 将足迹地图部署到你的博客

将足迹数据修改完毕后，将**项目传到你的 github 中进行托管，然后启用你的足迹地图项目的 github Page 服务，会得到服务地址： http://xxxx/xxxx/.**

![图片放大查看](https://sunyunzeng.com/%E5%8D%9A%E5%AE%A2%E4%B8%AD%E6%B7%BB%E5%8A%A0%E8%B6%B3%E8%BF%B9%E5%9C%B0%E5%9B%BE/%E5%9B%BE3.png)

**然后利用 iframe 将足迹地图内嵌到你博客中的相应位置，示例代码如下：**

```html
<iframe scrolling=no style="min-height:480px !important;" src="http://xxxx/xxxx/index.html" width="100%" height="100%"></iframe>
```

其中嵌入的样式可以根据自己需求修改。

# 进一步的样式调整

默认的地图为中国地图，足迹点的样式及背景样式都是固定的，如果想对足迹地图进行进一步的定制化，可以对 **/css/index.css 及 /js/index.js 文件进行修改**。

其中 **/js/jquery-jvectormap-cn-merc-en.js**为中国地图，你可以替换为世界地图，具体操作见 https://jvectormap.com/。

足迹地图依赖的是 **JVectorMap**，关于基本的样式定义可以参考官网 https://jvectormap.com/documentation/javascript-api/jvm-map/。


![jvectormap](https://www.u396.com/wp-content/uploads/2014/09/jvectormap.jpg)

# 续

- 文章首发 https://sunyunzeng.com/%E5%8D%9A%E5%AE%A2%E4%B8%AD%E6%B7%BB%E5%8A%A0%E8%B6%B3%E8%BF%B9%E5%9C%B0%E5%9B%BE/

- 项目地址 https://github.com/SUNYunZeng/FootprintMap

- 参考 http://www.wujiayi.vip/index.php/archives/52/