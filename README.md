# PromVerify

## 芝士甚么

~~芝士雪豹。~~

这是为福州 Prom2024 毕业舞会写的简单验票工具，基于 Node.js 的 express 框架。部署后，可以实现多个客户端同时连接并实时共享进出场数据。实时同步通过一个简单的 Web Socket 连接实现。

代码比较简陋，但是这不重要，反正就用一下。

前端用了 Vue，用 PinyinPro 显示姓名拼音，防止不会读人家名字导致当场社死。

## 抽号机部分

抽号机部分来自苯人初中时写的号数抽取器，原生 JS。仅抽取在场的人。

## 食用

数据的导入解析在前端的 excel2Obj 函数，接受 Excel 复制来的纯文本（Tab 分割的表），数据项认表头，表头的名字写在代码里面了，每个人的字段包含姓名、身份证号、手机号、学校（单位）、单号、是否双人票，这些都写死在代码里，有需要可以自行修改。数据导入都没有做有效性验证，有需要自己加。有对于双人票的支持，双人票的 `union` 属性为 `true`。双人票的框框里会显示另外一个人的名字和入场状态，且双人票共享同一个单号。需要注意， **身份证号是数据的主值** ，每个人必须唯一，如果没有也应该摇一个随机的出来。

后端数据明文存储在根目录下面的 data.json，没有会自己创建。

前端页面进入之后，右边的数字面板可以搜索身份证号、手机号和单号。左侧显示人员，红色是没入场，绿色是已经入场。入场情况统计会显示在顶上。

## 部署注意事项

**没有做任何安全性考量。** 没有鉴权。没有数据有效性验证。验票部分引用的 Vue 是开发版本，前端代码没有混淆且暴露在全局，服务器端数据也是全部明文存储。

介意的自己做。

## 有关福州 Prom 的一些废话

在这里发一点牢骚，我们这届完全在亏本的边缘，~~现在才六十多个人报名~~，往年是 200+ 的。宣传真的很难做。

感谢福州一中万能的家长们和一位赞助商的帮助，我们这一届活下来了，实际到场人数 140+。虽然出了一些状况，但好歹是办下来了。

不知道以后还能不能办得下去。如果后继有人的话欢迎把这个项目改改接着用。

以及，本次的文案基本上是 GPT4 生成的（有令其参考往年的文案）。后来想想，如果自己写的文案还没到 GPT 的水平那干嘛还自己写（）

*下面内容复制自 Prom2024 宣传文案*

### Prom 2024 ·「夏梦拾芳」

「夏夜的微光，拾起一抹芬芳。」
 
这是一场盛夏的约会，一个关于花与梦的故事。

我们在这里创造记忆，用花香铺展的走道，迎接属于我们的夏日梦境。
 
花，既是美丽浪漫的仪式，也是传情达意的载体。

花，可以是入场式的花瓣打卡墙，可以是尽情舞蹈时余光瞥及的装饰，也可以是创意环节中送给心动之人的小小惊喜。

花，象征着每个独一无二又绚烂多彩的个体，象征着活力朝气的青春，也象征着一路生花的未来。

这场青春的盛宴，属于你，属于我。
一段崭新的旅程即将开始啦！

Prom，即毕业舞会，为一种正式的舞会形式，一般在高中毕业期间举办，男女皆着盛装出席，是高中学业结束，迈向社会或大学的一场盛大的仪式。2017 年，福州一中 2017 届校友卓迅先生牵头策划了第一届舞会，代代传承至今。
 
Prom2024，已经是福州一中毕业生举办 Prom 的第八个年头， **首次无限制面向全福州市高三毕业生及往届学长学姐开放。** 欢迎各校的朋友们参与！
