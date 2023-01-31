# -本文搬运自https://dajuanzhan.cf/?id=646
本人小白，第一次写博客，求求各位大佬手下留情（可怜）！  
不废话，先上图  
![图片](https://user-images.githubusercontent.com/118042225/215646298-13daecb7-252f-4a21-8af0-84ba6d2f8878.png)  
可以看到，这个跳绳数目肯定不是光靠挂机开虚拟摄像头就可以做到的，而是引入了一种游戏修改的方法（天天跳绳不算游戏吗），就是  
### GG修改器  
![图片](https://user-images.githubusercontent.com/118042225/215646578-3703f1f7-7add-4b38-aff5-30d72d3e9c1f.png)  
其实不只是跳绳数目，大部分项目（除了跑步外）都可以用GG修改器刷分数。  
我们今天教大家修改其中的一个项目，也是最有技术的项目——自由跳绳的数目修改。  
# 声明：本文参照了https://www.bilibili.com/video/BV1Be4y117Uw/?spm_id_from=333.337.search-card.all.click  
但是经过了作者自己的尝试，提出了一种更加简便的方法。  
## 0:准备工作  
### 1.如果你有已经root的真机那就用真机，如果没有或连root是啥都不知道，请使用电脑上的安卓模拟器。  
注意：由于天天跳绳存在检测机制，大部分安卓模拟器打开天天跳绳会崩溃，目前仅有Mumu模拟器和Android Studio(简称AS）可以幸免！  
如果有Android Studio请自行使用AS，这里讲适合小白的Mumu模拟器  
请点击链接，下载Mumu安卓6（一定要安卓6！）  
https://mumu.163.com/  
### 2.下载好Mumu模拟器后请点击右上角的三条杠  
![图片](https://user-images.githubusercontent.com/118042225/215647048-563d3329-eb9a-46f4-bc5d-fa823326686a.png)  
然后设置中心——基本设置——在最下面打开root  
![图片](https://user-images.githubusercontent.com/118042225/215647271-17689974-e7c6-44b4-a587-4db804480389.png)  
接着需要下载两个软件：  
#### （1)天天跳绳（百度搜索自行下载）  
#### （2）GG修改器，请在Github下载或者在官网下载模拟器版本https://gameguardian.net/forum/files/file/2-gameguardian/
然后你要会安装GG修改器，其实root之后按照安装提示就好了，工作模式选择root，然后弹出的授予超级用户权限给它授予一下就好了，如果你连安装都不会建议去百度找一下教程  
### 3.虚拟摄像头  
有OBS或其他的自备，这里没用过虚拟摄像头的推荐跟我一起用Wecamhttps://www.e2esoft.cn/downloads/  
下载wecam视频演播室并安装，这里简单说一下使用方法  
你需要准备一个天天跳绳的作弊跳绳视频，比如https://www.bilibili.com/video/BV1Rg411h7hW/?spm_id_from=333.337.search-card.all.click  
你需要下载这个视频或者录屏让这个视频保存在本地  
然后导入右侧的视频播放列表，比如  
![图片](https://user-images.githubusercontent.com/118042225/215647468-80efb8e5-84be-4e52-be6f-05667a959928.png)  
然后点击右下角的播放按钮就是播放视频  
这时候你的摄像头就变成了这个视频中的内容  
当然，这样肯定是不够的，因为按照这个节奏刷十万个起码一个月  
那么接下来正式的修改教程  
## 一：第一次尝试  
我们打开天天跳绳，选择跳绳，然后选择自由跳绳，如果你的虚拟摄像头正常打开，那么就能检测到，如图：  
![图片](https://user-images.githubusercontent.com/118042225/215647784-b20d49ed-7ddd-44e6-bd19-1af66af4f9c5.png)  
这里有一个小概率事件，就是明明打开了死活检测不到，可以退出重进一下模拟器  
先让她跳几下，然后在Wecam中停止视频  
![图片](https://user-images.githubusercontent.com/118042225/215647972-fd728e31-48ab-40f3-bdc1-ad6df08faecc.png)  
这时候我们跳了6下，如果你正确运行了GG修改器，就会看到GG修改器图标的悬浮球（如图）  
点击悬浮球，打开GG修改器，点击左上角选择应用进程  
![图片](https://user-images.githubusercontent.com/118042225/215648087-1cc80ac4-3f74-4dce-bb19-5b4320b2800e.png)  
然后选择天天跳绳（第一个）进程  
注意:不要选择下面这个pushservice，我们需要抓取的是主进程！    
然后我们可以看到，工具栏有很多你不知道怎么用的工具，这里我们选择从右往左第二个，就是那个放大镜图标，点击打开精确搜索菜单  
![图片](https://user-images.githubusercontent.com/118042225/215648200-4fe4bbff-7807-41ca-ae91-5aae261d329a.png)  
我们需要在数值那边输入刚刚我们的跳绳数，然后点击类型，选择第二个Dword（这一步很重要！原理后面会写一篇解释）  
选好后点击下面的新搜索，然后可能会弹出一个提示“搜索助手：找到：xxxxx个结果”  
一般第一次搜索都会找到几万个结果  
没关系，我们再播放视频让她多跳几个，比如跳到13个。  
然后暂停，继续调出刚刚的搜索框，数据类型还是Dword保持不变，然后把值改成13  
![图片](https://user-images.githubusercontent.com/118042225/215648286-bd503dd5-b980-4207-8393-9dda5b0cce74.png)  
然后不要再新搜索了，要点击右下角的改善。  
这时候就会发现结果少了非常多  
## ————————————分割线——以下内容为2023.1.30日更新————————————  
![图片](https://user-images.githubusercontent.com/118042225/215648621-da8a9239-d7a1-4e6f-9989-e64f027b035c.png)  
我们要反复上述的改善步骤，直到结果数目<=60个左右（比如我这里就只剩几个了）  
然后我们点击上面菜单栏从右往左的第三个，就是那个带一只笔的图标的，点击打开修改框  
![图片](https://user-images.githubusercontent.com/118042225/215649078-22ce9af2-c2aa-4b1c-a01c-566988db3cdc.png)  
然后输入一个一想要的数字，点击确定进行修改  
![图片](https://user-images.githubusercontent.com/118042225/215649245-7b3f1559-908d-43a9-9551-a3ab6d4d4129.png)  
这时候就把有关跳绳数目的数据都修改完了  
![图片](https://user-images.githubusercontent.com/118042225/215649288-87bd447d-801e-476e-8095-21b63fe185c7.png)  
然后我们要解释一下：  
天天跳绳通常将跳绳数目存储在两个不同的类型中：  
一个是Dword:用于检验跳绳数目；还有一个是Double:由于记录跳绳数目  
所以我们刚刚只是改了校验，还需要改Double  
我们再次点击从右往左的第二个放大镜图标，这次把类型改成Double,值不变（比如我就还是搜索13，不要改成你刚刚修改的数值）然后点击新搜索（不要点改善！！！）  
![图片](https://user-images.githubusercontent.com/118042225/215650530-c1dcad71-d557-4075-95b4-be27310c6764.png)  
这次一搜就确定了三个结果，double相对Dword比较容易确定数据位置，基本上一次就可以了  
还是点击从右往左第三个的笔图标，像修改Dword一样修改Double,记住！两次修改后的数据要一样！！  
![图片](https://user-images.githubusercontent.com/118042225/215650600-36bb8264-d275-4fc4-a460-57d8ec642333.png)  
然后修改完会发现为什么右上角的数目没动？  
别急，我们直接点右下角的退出看看……  
![图片](https://user-images.githubusercontent.com/118042225/215650656-cf9c49ea-fe2e-4d6a-976f-19a955ca6143.png)  
修改生效了！  
但是当我们迫不及待地点击查看报告，却看到了这么一行字：  
![图片](https://user-images.githubusercontent.com/118042225/215650722-67e72baf-90da-4383-9f41-ae48f50c6536.png)  
也不奇怪，因为在天天跳绳里面，我们可是一分钟9000多下的奇人，不出异常才怪：  
![图片](https://user-images.githubusercontent.com/118042225/215650783-b329ea41-bc7d-439b-9ca6-b500bb9f4a39.png)  
那么我们该如何让自己的修改登上排行榜呢？  
不急，我们先点开跳绳排行榜，看看一分钟跳绳的榜单：  
![图片](https://user-images.githubusercontent.com/118042225/215650873-9656cdb1-ce93-4bb6-bfec-262793726483.png)  
可以看到，前几名都是清一色的四百下  
不是改不了更高的数据，而是天天跳绳里面有一个机制；一分钟跳绳数目>400下，自动判定你作弊  
但是自由跳绳很特殊，因为没有时间限制，你可以一直跳，连续跳2，3000下都可以  
那么如何判定你是否作弊呢？？？  
这里涉及到一个小学文化程度的计算公式：  
一分钟跳绳数目=自由跳绳总数目/跳绳总时长  
所以显而易见，我们需要修改跳绳总时长  
## ————————————分割线————2023.1.13日更新——————
## 二：第二次实战  
我们不多赘述，先把学到的修改方法操作一遍，操作到修改完Double这一步，如图：  
![图片](https://user-images.githubusercontent.com/118042225/215651138-5d4588ae-e4d4-4f54-9289-14ff1f93fa4e.png)  
然后我们先不急着退出看结果，而是直接返回桌面，点击系统应用——设置（因为我们要在设置里修改时间）  
![图片](https://user-images.githubusercontent.com/118042225/215651209-767b8815-8cf2-48e9-a88e-4f660dbc2175.png)  
然后在设置中找到日期和时间  
![图片](https://user-images.githubusercontent.com/118042225/215651270-748712da-b0af-42f5-8c0a-d219b7ee997e.png)  
 首先你得关闭最上面的自动确定日期和时间，然后点击下面的设置日期：  
 ![图片](https://user-images.githubusercontent.com/118042225/215651342-a7e2d1d0-88a9-4cde-bdd8-79d79762c519.png)  
 这里需要把日期设置成你今天日期往后n天（注意，重要的一步来了）  
举个例子：我今天是2023.1.31，然后我修改器1000000下，那我大概把日期往后推一个月，设置成2023.2.21  
![图片](https://user-images.githubusercontent.com/118042225/215651433-31f4151f-7695-41a3-854d-4412bf38d88f.png)  
这里的"n"取决于你修改跳绳的数目（从前面的公式也可以看得出来），你修改的数目越大，你往后推的日期就得越多。  
一般我习惯于修改一个一百万，这样大概时间改成往后推一个月就好了。  
注意：不要将跳绳数目修改的太大，也不要将时间往后推的太多，适量就好，一般改个1000000就差不多了。  
原因后面会讲。  
现在我们改好后直接点击确定，然后返回天天跳绳，就会发现跳绳已经自动结束了  
![图片](https://user-images.githubusercontent.com/118042225/215651565-5767f461-6a10-498a-a49b-98206db115ec.png)  
这是我们发现评价结果是A+，其实这个评价结果取决于它计算出来你一分钟的跳绳数目，因为我们修改了时间，所以系统判定你从2023.1.31跳绳到了2023.2.21,时间多了，一分钟跳绳数目自然降下来了，所以就解决了非法数据的问题。
![图片](https://user-images.githubusercontent.com/118042225/215651625-645801b5-f4de-40e1-8780-7055b17ce79b.png)  
可以看到，非法数据不在了！成绩也自然记录下来了，并且还可以参加排行榜！  
注意：即使你前面操作的滴水不漏，在最后一步点击查看报告的时候也有很大几率卡住加载不出来，成绩也自然不会记录，目前无解（抱歉啦）  
但是通过测试发现这种情况一般出现在你修改跳绳数目太多（一般是在修改数目>100万的时候，修改数目<100万很少出现）或者往后推的日期太多（一般往后推的日期<2个月）  
如果你一切正常并且修改成功，就赶快去排行榜看看叭！  
![图片](https://user-images.githubusercontent.com/118042225/215651697-13227dd8-c73a-49af-9041-fe637dab1812.png)  
如果你很好奇为什么我只超过了8%的选手，是因为这个超过百分比是根据你系统算出来一分钟跳绳数目判定的。  
## 所以至此，跳绳的修改就正式完成
