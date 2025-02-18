readme.md
# UWP应用 WeatherHelper 天气助手
---

##开发环境
Windows10,visual studio2017

**项目名称**：WeatherHelper 天气助手 
**项目简介**：这是一个简单的于天气的 uwp 应用，用来查询天气，记录天气，以及对相关天气提供 出行建议。 
**项目功能**： 查询天气。通过 API 解析的方式，可以上网查询天气。有两种方法加入查询后的新的天气， 可以点击“我的天气”按钮，获取地理位置，直接查询天气。也可以在输入框里输入地址，使用完整英文名，既可以查找到相应地点相关天气信息。查询到的天气都会记录下来。 
**项目亮点**：1. 每个项目有两个按钮，可以点击 del 删除该项目，也可以点击 tips 按钮，获取天气的 相关建议   2. 项目以及内部内容会随着窗体大小的改变而改变，界面变大时，项目框体会变大。  3. 天气整理。查询后的天气会在界面中以项目的形式显示。可以通过左边的按钮，进行天 气筛选，筛选出相应的天气。


## 项目难点及解决方案 
**难点 1**：天气的获取。找 API 费了一些功夫，最后在 openweathermap 获取到了 API，但相应的代价是响应时间慢，且只能使用英文城市名。 构造了两个获取函数：一个是通过经纬坐标获得，另一个是通过城市名称获得,两种分别解析 API

**难点 2**：程序初始化的时候，想在加载的时候同时添加一些城市的天气项目进去。然而这个外网 API 访问速度不定，且访问间隔不能过短，否则都会无法访问。所以最后采取了查询几个城市的天气， 以 string 数据的形式直接添加。但是搜索这几个天气名称时，会更新数据并替代原有数据。

**难点 3**：管理添加的项目。作业中，建立了两个项目，Item 文件和 viewModels 文件。自己做项目的时候，没有新建第二个文件，而是在 WeatherItem 类中直接添加了一个 class，作为 Item 类的管理。用起来感觉不错 WeatherManager 即为管理类。通过使用 ObservableCollection<>类来管理项目，实现了项目的增减和筛选。

**难点 4**：UI 设计 照着教程做了一个汉堡菜单，自己对菜单里的内容进行了定义，并且选择了合适的图标作为 菜单图标。最上方的标题栏的位置安排也经过了不断改变，最终有一个比较好看的做法。

**难点 5**：自适应 UI。可能是由于缺少了某些 dll 的缘故，早在做这个项目的时候，如果用直 接往项目里添加 DataControl 元素的方法，VS 会找不到添加的控件，回报错。之后只能把控件写 到了 mainpage 内部，但也就不好做相应的调整。不过依然可以用相应的控件做出自适应 UI，可 以根据窗口大小改变项目小框体的各项显示。

## 总结

制作人：软件工程 16340167 马显然

在综合实训过程中，由于一些原因导致了原小组解散，所以未能按时提交一个完整的制品。
这个应用是现代操作系统课程的期末作业，同样因为组不到队的原因，这也是我个人的制品，其中并没有很新颖的功能的项目，但我的目的是做出一个尽可能涵盖较多知识点的应用，也是一己之力尽力而为做出的一个比较完整的应用成品。
