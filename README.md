## Wbooru插件市场
  此Repo通过Issues作为核心成Wbooru的插件市场，Wbooru程序可以通过此Repo的Issues获取可以下载或更新的插件以及其他功能实现。<br>
  任何插件作者也能在Issue按照指定格式发布Issue来公布他们的插件，也能按照指定的格式添加Issue的评论来更新插件的版本发布。


  ### **如何发布自己的插件?**
  ![](https://puu.sh/EX1We/dc8742497a.png)<br>
  创建新的Issue，标题随意，但建议起只和插件名字相关的名字。<br><br>
  然后在正文创建**Markdown标准的两列多行表格**。然后请按照以下表格描述来填写此表格：
  <br>
  
Property名|描述
--|--
|PluginName|插件名, **必须** 和插件 **PluginInfo继承类中的PluginName属性** 一样,比如图中PluginName的值"`BossKey`"在[**这里**](https://github.com/MikiraSora/WbooruPlugin.BossKey/blob/master/BossKeyPluginInfo.cs#L25)是相同的|
|PluginAuthor|插件作者，建议和 **PluginInfo继承类中的PluginAuthor属性** 一样|
|Description|插件描述，建议和 **PluginInfo继承类中的PluginDescription属性** 一样|
|ReleaseType| （可选）发布类型，表示获取此插件版本信息和下载信息的来源方式，若填写`GithubRelease`则表示此插件的下载和更新信息都可从Github公开Repo的Release页面去获取。若 **省略不填写此属性** ，则Wbooru会根据此Issue页面的评论来获取相关信息。|
|ReleaseUrl|如果填写了ReleaseType，则必须填写此属性，若ReleaseType为`GithubRelease`,则ReleaseUrl必须填写为此插件公开repo地址(比如https://github.com/MikiraSora/WbooruPlugin.Yandere),Github Release发布的也有一定的**要求**|

<br>
按照规定填写完以上表格后，会有Wbooru相关负责人来检查以上内容是否符合规定，之后会给此Issue添加一个`Plugin-Release`标签。只有含有此标签的Issue，才会被Wbooru识别并在插件市场页面显示。


#### **若ReleaseType为空，发布新版本的插件** ( [例子](https://github.com/MikiraSora/Wbooru.PluginsMarket/issues/3) )
在对应的插件Issue页面添加新评论，页面添加**Markdown标准的两列多行表格**,然后请按照以下表格描述来填写此表格:

Property名|描述
--|--
|Version|插件版本号，**必须**和**插件本体dll的版本** 相同,比如格式为`v1.2.3` |
|ReleaseType|发布类型,`Stable`表示**稳定版/正式版**,`Preview`表示**测试版/预览版**|
|DownloadURL|下载地址，必须提供zip标准文件，此压缩包将会解压在Wbooru根目录，所以建议按此格式压缩:![](https://puu.sh/EX2pX/b08a538c50.png)|
|ReleaseDescription|此版本发布的描述内容，一般是changelog|


#### **若ReleaseType为GithubRelease，发布新版本的插件** ( [例子](https://github.com/MikiraSora/Wbooru.PluginsMarket/issues/1) )

* 请在插件的Release页面发布新的Release,若勾选了`This is a pre-release`页面则表示此发布是预览发布，和上表ReleaseType的`Preview`等同，反之和`Stable`等同.
* 上传的文件也和`DownloadURL`一样上传同样格式和要求的zip标准文件。
* Tag version必须以上表`Version`格式一样
* Release正文和上表`ReleaseDescription`等同
* Release标题随意
