# 1. 项目名称——实评

API 驱动之智能产品 MVP加值主张宣言：目前市场中还未出现关于对商品评价文字进行分析，以获取真实有用评价的app产品。该产品利用API，快速有效地分析评论，确认该评论是否为真实的用户在体验过商品后所得出的感受。

核心价值宣言：该MVP中，用到的API类型有：评论观点抽取、情感倾向分析、文本审核和商品图片搜索等。该产品是一款来帮助用户从众多繁杂的评论中筛选出真实的对自己有用的评价，解决用户在筛选商品或服务中无法确认已购用户评价真实性问题的APP，为需要得到真实商品反馈的用户提供更优的处理解决方案。

问题情境（用户痛点宣言）：用户希望在网上购买商品，却因为评价充斥着大量的刷好评、虚假广告等情况，而无法判断该商品的真实情况。在大量的文字中无法快速寻找到关键信息。

解决方案：用户在选择商品时，利用该产品通过已购买客户对商品的真实反馈来作为判断，在良莠不齐的商品评价中，排除掉那些恶意竞争产生出的毫无用处的评价，从而在购物中挑选到更加优质更加适合自己的产品。

AI概率性考察：或许会出现极其隐蔽的垃圾广告或低质灌水，无法被该产品识别到，并列入可用数据呈现给用户，影响用户体验。但因为只是个别例子，且此时已在筛选留下有用信息后，所以带有个别没有被发现的垃圾评论依旧比原数据更有价值，更方便用户辨别评价的价值。在后续，通过API数据集的不断完善扩展，这些垃圾信息也会越来越少，并不影响价值主张为底线。

## 2. 问题表述与需求列表

了解发现，有许多人不满于商品评论中存在大量刷评论现象，表示其会影响自身购物的判断，因此想到该API驱动之智能产品App——实评。

有谁需要？：该产品给需要网购却因为评论问题难以下手购买的人提供帮助。

为什么做？：解决因为评论夹杂着各种无关信息，无法快速准确判断商品质量等问题。

用户画像：

- 人群：会网购的人群
- 年龄：16~45岁
- 特点：喜欢上网，对新鲜事物保持好奇
- 用户需求：了解到最真实的商品使用情况

![](/img/多方利益.png)

### 2.1 问题表述

需求项：

1. 大量的评论和大篇幅文字让用户需要花费大量时间去寻找真实有用的评价
2. 刷屏的虚假广告和垃圾评价，使用户要在其间找到有用的评价十分困难。
3. 无法从评价中快速获取到关键词及使用后真实情感。

![](/img/价值主张画布.png)

### 2.2 需求列表

| 优先级 | 需求 | API名称 | 智能加值？ | API类型 | 平台名称 |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 1 | 从大量的文字评价中快速抓住关键信息及标签分类 | 评论观点抽取API | 是 | 自然语言处理 | 百度 |
| 2 | 去除无用评价（低质灌水、垃圾广告等） | 文本审核API | 是 | 自然语言处理 | 百度 |
| 3 | 用以区分 已购用户被迫好评但给出真实的不良评价 | 情感倾向分析API | 是 | 自然语言处理 | 百度 |


## 3. 解决方案原型表述

该产品的功能是分析用户上传的商品的评价，对其进行处理得到用户需要的结果。

一分钟展示原型交互

![1分钟展示](/img/API原型.gif)

点击下方链接，了解产品更多内容。

[产品原型试用](https://modao.cc/app/62821057a3ed22883155a4244906fb4cc5579192?simulator_type=device&sticky)

[点击下载原型PPT](https://gitee.com/Tengzyi/API/raw/master/API%20%E6%BB%95%E5%8D%93%E6%98%93%20181013007.pptx)

### 3.1 界面流程及关键智能交互

进入首页后，通过文字识别或拍照识别的智能交互进入不同的搜索页面，让用户选择不同的方式，进入到所选的商品详情。点击商品分析，进入分析页面，即可查看该商品以下在通过审核后排除掉无用评论后的有价值。(Viability商业可行性)首先，可以看到该产品将各评论进行分析，通过情感倾向将评论分为好评和差评，并根据其内容制作标签形式，使用户对商品有最基本的认识。（Feasibility技术可行性）接着将其中的评论进行颜色化处理，让用户一眼就能看出评价中的关键信息，对商品有了更进一步地认识。还有最后的图表分析页面，该产品将观点进行抽取获得气泡图，使商品的主要评价标签一目了然，并将商品的观点聚类，让用户对商品价格、服务等方面有了更清晰地判断，实现MVP价值体现。（Desirability用户可欲性）

以下为交互界面流程图DFD
![](/img/交互界面DFD.png)

以下为关键智能交互的前后的界面设计

![](/img/首页.png)

![](/img/拍照.png)

![](/img/搜索.png)

![](/img/分析前.png)

![](/img/分析.png)

![](/img/标签.png)

![](/img/审核.png)

![](/img/图表.png)

### 3.2 数据流程及关键智能API使用

API驱动智能流程方面，首先在首页上有复制链接及拍照上传两种方法，通过文字识别或拍照识别的智能交互将用户搜索的商品信息上传至后台数据库，并匹配到对应商品的评价部分对其使用评论观点抽取、情感倾向等关键智能API结合，最后将分析结果显示在App的后续页面（Feasibility技术可行性）。处理数据为用户显示一目了然的评价标签，并制成图表，使用户对该商品内的评价有更直观的认识，为之后用户的购买选择提供一个参考方向(Viability商业可行性)、，解决了用户无法通过真实评论购买商品的问题（Desirability用户可欲性），实现MVP价值体现。


以下为数据流程图DFD
![](/img/数据DFD.png)

API代码：

![API调用](./img/API调用.png)

```
# 评论观点抽取API

>request_url = "https://aip.baidubce.com/rpc/2.0/nlp/v1/lexer"

text = "在这家店买过好几次了，是回头客。口味还是一如既往的好吃，就是份量太少太少，价格太贵，而且快递太慢了。"
text1 = text.encode(encoding='UTF-8')
print(text1)

params = {
    "text":text
}
access_token = '[24.975e3fd3d1ee178564cf69c80a1f6527.2592000.1597678710.282335-21463884]'
request_url = request_url + "?access_token=" + access_token + "&charset=UTF-8"
headers = {'content-type':'application/json'}
response = requests.post(request_url,data=json.dumps(params),headers=headers)

response.json()
```

```
# 文本审核API

request_url = "https://aip.baidubce.com/rest/2.0/solution/v1/text_censor/v2/user_defined"

text = "在这家店买过好几次了，是回头客。口味还是一如既往的好吃，就是份量太少太少，价格太贵，而且快递太慢了。"

params = {"text":text}
access_token = '[24.975e3fd3d1ee178564cf69c80a1f6527.2592000.1597678710.282335-21463884]'
request_url = request_url + "?access_token=" + access_token + "&charset=UTF-8"
headers = {'content-type':'application/x-www-form-urlencoded'}
response = requests.post(request_url,data=params,headers=headers)

response.json()
```

```
# 情感倾向分析API

request_url = "https://aip.baidubce.com/rpc/2.0/nlp/v1/sentiment_classify"

text = "在这家店买过好几次了，是回头客。口味还是一如既往的好吃，就是份量太少太少，价格太贵，而且快递太慢了。"

params = {
    "text":text
}
access_token = '[24.975e3fd3d1ee178564cf69c80a1f6527.2592000.1597678710.282335-21463884]'
request_url = request_url + "?access_token=" + access_token + "&charset=UTF-8"
headers = {'content-type':'application/json'}
response = requests.post(request_url,data=json.dumps(params),headers=headers)

response.json()
```

API试用链接：

[文本审核API](https://ai.baidu.com/tech/textcensoring)

[情感倾向分析API](https://ai.baidu.com/tech/nlp_apply/sentiment_classify)

[评论观点抽取API](https://ai.baidu.com/tech/nlp_apply/comment_tag)


API测试代码技术文档：

[文本审核API](https://ai.baidu.com/ai-doc/ANTIPORN/Rk3h6xb3i)

[情感倾向分析API](https://ai.baidu.com/ai-doc/NLP/zk6z52hds)

[评论观点抽取API](https://ai.baidu.com/ai-doc/NLP/tk6z52czc)

数据简介：

评论观点抽取：自动抽取和分析评论观点,帮助您实现舆情分析、用户理解，支持产品优化和营销决策

情感倾向分析：对包含主观信息的文本进行情感倾向性判断，可支持在线训练模型调优效果，为口碑分析、话题监控、舆情分析等应用提供帮助

文本审核：一站式检测文本中夹杂的色情、推广、辱骂、违禁、涉政、灌水等垃圾内容，净化网络环境，为您的应用提供更可靠的内容安全保障

人工智能概率性考量：或许会出现极其隐蔽的垃圾广告或低质灌水，无法被该产品识别到，并列入可用数据呈现给用户，影响用户体验。但因为只是个别例子，且此时已在筛选留下有用信息后，所以带有个别没有被发现的垃圾评论依旧比原数据更有价值，更方便用户辨别评价的价值。在后续，通过API数据集的不断完善扩展，这些垃圾信息也会越来越少，并不影响价值主张为底线。

## 4. 学习/实践心得总结及感谢

学习心得：通过API人工智能这门课的学习，我了解到了许多有关API的知识，更加深入地明白了API调用的机制，更清楚地了解到高德地图等产品部分功能实现的具体过程。在通过查看官方文档并成功调用API的时候，让我真切地感受到科技带来的便利以及API的强大和易操作，即使是初学的小白，也能立刻掌握并实现功能。总结：在调用API时，如果出现了各种报错问题，建议多查看API使用文档。

感谢[百度AI开放平台](https://ai.baidu.com/)是他们的支持让我对API有了更深刻的理解，并将其API（我用到的API有：评论观点抽取、文本审核、情感倾向分析）运用到我的产品中，更加完整了我的产品，为其提供了技术帮助。感谢[墨刀平台](https://modao.cc/)提供的免费产品原型制作，让我初步完成了“实评”App的原型。感谢[processon网站](https://www.processon.com/)，使我完成了流程图的制作。