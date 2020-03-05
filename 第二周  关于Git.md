# 第二周  关于Git

##### （廖雪峰官方教程的一点总结👀）

## 一、Git是什么

* ### 官方语言：Git是目前世界上最先进的<u>**分布式版本控制系统**</u>（没有之一）

那git能干什么呢，主要是以下的几个用处：

1. Git 会跟踪每个文件的修改，删除，以便任何时候都可以追踪历史或者在将来某一时刻可以还原（版本控制  最基本）
2. Git的分布式使用的分支管理操作简单，安全可靠

* ### git的诞生

* 说起git的诞生着实不得不让人直呼一声nb！

Linux的创作者仅仅用了两周的时间用**C语言**写出了git！（两周。。同样是两周我闷在家里自我隔离TAT，别人写出了如今最流行的分布式版本控制系统，肃然起敬啊。。)

* ### 集中式/分布式版本控制系统

  1. **集中式分布系统**有一个大型的中央处理器所有的数据、运算、处理任务全部在中央计算机系统上完成（虽然不太容易坏，不过确实它坏了大家就都完了。。）
  2. 每一个终端用来输入输出。
  3. 集中式版本控制系统最大的毛病就是必须联网才能工作。
  4. 终端多的时候速度会变慢
  5. 如果终端用户有不同的需要，要对每个用户的程序和资源做单独的配置，在集中式系统上做起来比较困难，而且效率不高。

pk

1. **分布式版本控制系统**没有“中央服务器”，每个电脑上都是一个完整的版本库，不需要联网
2. 分布式版本控制系统的安全性要高很多，因为每个人电脑里都有完整的版本库，当一台机器发生故障时，可以使用另一台主机的备份。简单的说就是有福同享，有难不同当😄。
3.  用户可以根据自己的需要在自己的主机上安装不同的操作系统、应用软件，使用不同的服务，不再像集中式计算机系统那样受限于中央计算机的功能。

当然分布式系统除了git还有别的，但是git还是最快最简单也最流行~

## 二、如何安装git

这个这里就不详细写了😀

廖雪峰官方：https://www.liaoxuefeng.com/wiki/896043488029600/896067074338496

这里介绍的很详细欧，不行还可以Google，bing，百度，360等。。。

## 三、版本库

就是储存项目的地方（他就可以追踪还原历史版本啦）

* #### 首先我们来创建一个仓库

* 打开git（这里我用的是windows  别骂了o(TヘTo)我知道辣鸡啦）

* *这里我新建了一个名为second的文件夹

* ![image-20200302104439149](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200302104439149.png)





* 然后在这个second文件夹里就会有一个`.git`的文件，但是一般自动隐藏了，需要取消隐藏

<img src="C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200302110900425.png" alt="image-20200302110900425" style="zoom: 67%;" />



* #### 好的，然后我们可以在这个仓库上传我们的文件了

* 首先我们把需要<u>上传的文件都写进second</u>里面（也可子文件夹）

* 👀这里我创建一个名为text的txt

<img src="C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200302115435999.png" alt="image-20200302115435999" style="zoom: 80%;" />

* 更改test里的内容
* ![image-20200303085453890](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303085453890.png)

* 然后把文件添加到版本库（`git add`）
* 但是没有任何的显示👀   嗯那就对了√
* 这里可以反复多次使用添加很多文件欧
* emmmm，偷偷告诉你`git add .`可以把文件夹所有文件一下子添加进去hhh

![image-20200303083357640](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303083357640.png)

* 接着把文件提交到仓库----->`git commit -m"这里一定要写说明！！为了让你和你的小粉丝都知道这是一个什么文件😀"`
* 然后他就会告诉我们👀1.一个文件被改动（添加的文件）2.插入了1行内容（因为我的test里有1行内容）

## 四、猜猜我变了没有啊

* 现在我们来看看`git status`命令

![image-20200303090509456](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303090509456.png)

* 当我修改了test的内容时候
* ![image-20200303090753543](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303090753543.png)
* 上面的命令输出告诉我们，`readme.txt`被修改过了，但还没有提交我的修改。
* 那我们怎么用git知道修改了什么内容呢
* ![image-20200303091445359](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303091445359.png)
* 当我们再次add之后输入 `git status` 就会看见它告诉我们准备提交要修改的内容了

![image-20200303091733832](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303091733832.png)

![image-20200303091822160](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303091822160.png)

* 然后提交 就会告诉我们 +了两个地方 -了一个地方
* ![image-20200303092234711](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303092234711.png)

## 五、以前的我

版本回退是git最基础的一个功能

* 首先我们要先看看有多少个版本

![image-20200303093608604](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303093608604.png)

* `git log --pretty=oneline`（前面一大串乱码样的东西就是版本号）

![image-20200303094032269](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303094032269.png)

* 好的，现在我们可以来回退啦
* 在Git中，用`HEAD`表示当前版本，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。

![image-20200303094453676](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303094453676.png)

* 这里就回退到上一个版本啦
* 那么现在我后悔了怎么办
* 害！可是世上没有后悔药啊T.T
* hhh但是git有👀
* 方法一：如果刚刚的命令窗口还在，可以看见版本号

![image-20200303095311717](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303095311717.png)

* 方法二：万一我把窗口关了那怎么办呀
* ![image-20200303095619998](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303095619998.png)
* 

## 六、工作区与暂缓区

* 这里引用了廖雪峰老师的图，加了一点注释😀

![image-20200303100816081](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303100816081.png)

## 七、强大的管理修改

Git跟踪并管理的是修改，而非文件！

为什么这样说呢（此处引用廖雪峰的例子）

假设我们做出这样的修改：

第一次修改 -> `git add` -> 第二次修改 -> `git commit`

那版本库里的最新版本是什么呢

* 首先修改文本

![image-20200303102205309](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303102205309.png)

* 添加
* ![image-20200303102342653](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303102342653.png)
* 再修改
* ![image-20200303102500524](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303102500524.png)

* 现在提交  再查看一下
* ![image-20200303103102661](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303103102661.png)
* 咦，看来第二次修改没有被提交



* ##### 其实在六、的那个图里我们就知道，提交的只是在暂缓区的东西而不是原来文件里的东西，这大概就是廖雪峰老师说的管理修改而不是管理文件吧

那看来每次修改之后就要add，commit，修改的内容才能提交到版本库

## 八、撤销修改

1. 丢弃工作区文件   用命令`git restore`

   * 修改文本

   ![image-20200303105411215](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303105411215.png)

   * 这里提示我们使用`git restore`可以撤销工作区的修改

   ![image-20200303105939376](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303105939376.png)

   * 好的我们来输入一下

   * ![image-20200303110405452](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303110405452.png)

     

2. 丢弃暂存区的的修改  第一步用命令`git restore --staged` 第二步用命令`git restore`

   * 那如果已经把内容加到了暂存区了
   * ![image-20200303110743562](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303110743562.png)
   * 然后我们来查看一下
   * 它提示我们用这条语句可以把暂存区的内容撤销掉放回工作区（我觉得就是删掉暂存区这部分的内容）
   * ![image-20200303111014278](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303111014278.png)
   * 下一步
   * ![image-20200303111628119](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303111628119.png)
   * 然后就跟1.一样的操作撤销工作区内容
   * ![image-20200303112008225](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303112008225.png)

3. 已提交到版本库但没有推送到远程库（远程库内容在后面呀），看看五、版本回退叭

   

## 九、删除文件

这里是两种情况：

1. 确实要删除版本库里的文件
   * 用命令`git rm`删掉，并且`git commit`

​          * 这里我新建了一个t.txt并上传到库

![image-20200303112735990](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303112735990.png)

* 然后用`git rm`删掉并且提交，这样就确实被删了
* ![image-20200304104247660](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304104247660.png)

2. 是不小心在工作区删错了文件

   * 输入这一个命令原本被删掉的文件就又回来了

   * ![image-20200303113946099](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303113946099.png)
   * 注：其实这个命令是将版本库的版本代替工作区的版本，所以是我们最后一次提交到库的内容

## 十、<u>远程仓库</u>！！！

#### GitHub终于要登场了！

## 1. 添加远程库

首先注册一个GitHub账户吧（自己注册？？）

https://github.com/

然后创建SSH Key

![image-20200304114017689](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304114017689.png)

登录之后右上角，创建一个新的储存库

![image-20200304112734800](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304112734800.png)

然后：

![image-20200304112954219](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304112954219.png)



现在仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。



![image-20200304113354971](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304113354971.png)

跟着上面提示的操作，就可以把本地仓库的内容推送到远程仓库啦

![image-20200304114416650](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304114416650.png)

注：因为是第一次推送所以git push后面要加上 -u，以后的修改版本就不用啦

还有就是git是把远程库和本地库关联了起来呢，不仅仅是单纯的提交

现在仓库里就有内容啦

![image-20200304114747797](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304114747797.png)

这里还有一个警告！

![image-20200304114905193](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304114905193.png)

## 2.从远程库克隆

一般我们在日常工作中不会直接把项目库和远程库关联，而是克隆一份到远程库里。

先创建一个库

![image-20200304162215941](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304162215941.png)

创建好后：

![image-20200304162438441](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304162438441.png)

下面就是本地操作啦：

找到你要上传的文件夹项目，右键点击文件夹（注意：不能选单个文件或者压缩包）在选项里选择**Git Bash Here**

![image-20200304162911699](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304162911699.png)

然后来看文件夹

![image-20200304163150362](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304163150362.png)

然后我们将要上传的文件**复制**到demo文件夹里面

![image-20200304163827663](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304163827663.png)

上传

![image-20200304165609885](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304165609885.png)

这里要注意，第一次使用的时候要先配置好git上的用户名和邮箱

![image-20200304170012957](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304170012957.png)

然后再提交就🆗啦



## 十一、分支管理

* 什么是分支？相当于一根树枝，既与主干相连又不互相影响

就如廖雪峰所说：

![image-20200303205759305](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303205759305.png)

## 十二、创建合并分支

在上面版本回退的地方，我们已经知道，git把每一次提交串成了一条时间线，也就是一个主分支。

​     （六、里有一个具体的版本库内部构成图）

![image-20200303211530880](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303211530880.png)

现在我们来新建一个分支 `dev`

![image-20200303212102422](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303212102422.png)

然后我们可以修改我们的文件啦

![image-20200303212226774](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303212226774.png)

然后提交

![image-20200303212512769](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303212512769.png)

这时他就提交到dev分支里了，但是master主分支里是没有变的

如果我们完成了分支里的内容，现在来把他合并到主分支吧

![image-20200303213347404](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303213347404.png)

然后我们就可以删除dev分支了

![image-20200303214045962](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303214045962.png)

* ##### 因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在`master`分支上工作效果是一样的，但过程更安全。

创建/切换分支的第二种命令：

![image-20200303214344824](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303214344824.png)

## 十三、分支间的冲突

假设我们在一个分支上提交了内容，又在主分支（或者另一个分支）提交了另外的内容，那我们需要合并的时候会发生什么奇怪的事呢？

首先：

![image-20200303220547221](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303220547221.png)



然后我们就可以开始试着合并了：

![image-20200303221338632](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303221338632.png)

然后我们看一下test里的内容：

![image-20200303221538487](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303221538487.png)

git还告诉了我们不同分支的内容，害!

那现在我们就手动改一下吧

![image-20200303222934415](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303222934415.png)

这里用这个命令可以看见分支合并情况👀

![image-20200303224034309](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200303224034309.png)

## 十四、分支管理策略

上面我们提到合并分支时Git会用`Fast forward`模式，但这种模式下，删除分支后，会丢掉分支信息。

如果强制禁用`Fast forward`模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

现在我们来实践一下8：

![image-20200304085315434](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304085315434.png)

现在合并`dev`分支：

![image-20200304092001397](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304092001397.png)

* ##### 在正规的工作中，`master`分支非常稳定，一般仅用来发布新版本，平时都不在上面干活呢，干活都在`dev`分支上。

* ##### 也就是说，`dev`分支是不稳定的，到某个时候，比如1.0版本发布时，再把`dev`分支合并到`master`上，在`master`分支发布1.0版本。

* ##### 你和你的小伙伴们每个人都在`dev`分支上干活，然后每个人再<u>创建自己的分支</u>，时不时地往`dev`分支上合并就可以了。

## 十五、Bug分支

日常工作中我们一般会遇到以下几个问题吧：

1. 主分支发布的版本遇到了bug  0.0
2. 但是手头工作ing，要存档
3. 主分支的bug，工作ing的分支也有

首先先说说存档吧：

![image-20200304095652676](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304095652676.png)



现在我们就可以在有bug的分支上创建新的分支来修复啦：

![image-20200304100513947](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304100513947.png)



修复完了之后我们回到working分支来继续我们的工作8：

![image-20200304103418379](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304103418379.png)

注：其实我们开始是创建了一个地方来储存工作区的内容![image-20200304103603294](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304103603294.png)

然后假如我们工作的地方也有上面修改的bug，那怎样快捷的修改呢？

用`git cherry-pick `命令，把bug提交的修改“复制”到当前分支

![image-20200304105617588](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304105617588.png)

## 十六、强行删除分支

当我们开了一个分支working但是还没work完就不想要这个分支了怎么办？？

这时这个分支没有被合并过，我们要通过`git branch -D `强行删除。

![image-20200304111826390](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304111826390.png)

## 十七、多人协作

记得上面我们已经将本地仓库和远程库连起来了：



![image-20200304143651019](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304143651019.png)

* ### 推送分支

就是当我们修改了本地分支需要提交推送到远程库的时候啦，这里可以推送主分支也可以推送其他分支，看自己的需要哦（当然主分支是一定要的啦😄）

![image-20200304145325391](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304145325391.png)



* ### 抓取分支

在多人协作中一般都是大家从远程库把主分支clone下来

![image-20200304172419611](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304172419611.png)

然后创新的分支来改改改，然后再时不时的push到远程库里

![image-20200304172919663](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304172919663.png)

那没了，如果我也改了，我的小伙伴也改了那怎么办！！！

![image-20200304173431137](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304173431137.png)

没事~我们可以先git pull把小伙伴的最新提交抓下来，然后合并再传上去。

![image-20200304173829277](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304173829277.png)

但是要注意o，我们抓下来的是远程库的分支和本地库的是不一样的，所以我们要设置他们的链接o

![image-20200304174346352](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304174346352.png)

然后再pull（如果合并有冲突记得怎么做吗👀  不记得啦？那看看十三、）

好的现在就完事啦

![image-20200304174436135](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304174436135.png)

## 十八、*Rebase

git rebase是用来干嘛的呢，就是用来整理分支的，因为当有很多人的时候大家相互交错的上传就会让提交很混乱，然后如果要找回想要的版本就很困难。

但是在我们一般的开发中其实并不是特别常见的命令

然后因为我没有创建很多分支😅这里贴一个大佬的详解

https://blog.csdn.net/wangnan9279/article/details/79287631

当然还有我们廖雪峰老师的啦🤭

https://www.liaoxuefeng.com/wiki/896043488029600/1216289527823648

## 十九、标签管理

标签（tag）其实就是一个版本号，跟commit绑定在一起而比commit号简单有意义。

打标签也很容易的（给当前版本打）：

![image-20200304150128338](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304150128338.png)

那如果想给以前的版本打标签呢：

![image-20200304150630523](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304150630523.png)

注：标签不是按时间顺序列出，而是按字母排序的。

![image-20200304151240925](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304151240925.png)

注：用命令`git show `+版本号 可以看到说明文字：

![image-20200304151332149](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304151332149.png)

如果标签打错了：

![image-20200304151749400](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304151749400.png)

然后我们打的标签只是在本地，那么怎样推送到远程库呢？

![image-20200304152008698](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304152008698.png)

那如果要删除标签呢？

![image-20200304152247988](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304152247988.png)

然后：

![image-20200304152347784](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304152347784.png)

这样标签就被删除了

## （最后：最后来康康这个配置别名8   hhh）

干啥啥不行偷懒我最行嘻嘻嘻

status，branch。。。这些一堆一堆的单词对我这种英语渣渣真是要晕了

那怎么办呢？

嘻嘻嘻

![image-20200304155721372](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304155721372.png)

这里要注意一定要注意T.T

不要乱改.git的文件（但是为了偷懒我还是以身犯险了👀）

![image-20200304160126197](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304160126197.png)

然后我们来试一下8

啊这真是太爽了~~

![image-20200304160327090](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20200304160327090.png)



### （这里是整理的所有上面涉及的命令）

# git命令

* cd  文件名--进入子目录

* cd ../  ---返回上一级

* git init   --创建版本库（仓库）

* touch 文件名---创建所需文件

* git add  文件 ---添加到版本库

* git add .*  ----添加全部文件到版本库

* git commit -m”xxx“---把文件提交到版本库

* git status ---掌握仓库当前的状态（是否修改）

* git diff   ----查看不同

* git log ---查看版本数

* git log --pretty=oneline  ---简易版看版本数

* git reset --hard HEAD^  ---回退版本

* git reset --hard commit_id ---回到某版本

* git log ----查看提交历史

* git reflog  ---查看命令历史，确定要回到未来的哪个版本

* git restore ---将版本库版本代替工作区版本

* git rm  ----删除文件

* git check -b /git switch -c   ----创建/切换分支

* git branch    -----查看所有分支

* git merge ----合并分支

* git branch  -d    -----删除分支

* git status ---查看冲突

* git log --graph-----查看时间轴

* git stash-----存档

* git stash pop----恢复

* git cherry-pick+commit号-----复制别的提交到该分支

* git branch -D+xxx-----强行删除

* git remote -v----查看远程库地址信息

* git push origin  -----推送分支到远程库

* git tag ----打标签

* git tag -d ---删标签

* git show ----版本说明

  

  



