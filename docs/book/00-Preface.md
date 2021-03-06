

# 前言

> 本书基于 Java 8 版本来教授当前 Java 编程的最优实践。

在此之前，我的另一本 Java 书籍 Thinking in Java 第 4 版（《Java编程思想》 Prentice Hall 2006）对于 Java 5的编程依然有指导意义。Java 5 是用于 Android 编程的语言版本。

随着 Java 8 的出现，这门语言在许多地方发生了翻天覆地的变化。新的 Java 代码在使用和实现上与以往不尽相同。这也是为什么时隔两年后我创作了这本新书。《On Java 8》旨在面向已具有编程基础的开发者们。对于初学者，可以先在 [Code.org](http://Code.org) 或者 [Khan Academy](https://www.khanacademy.org/computing/computer-programming) 等网站上补充必要的前置知识。同时，[OnJava8.com](http://www.OnJava8.com) 上也有免费的 Thinking in C（《C编程思想》）专题知识。

与几年前我们依赖印刷媒体相比，像 YouTube，博客和 StackOverflow 这样的网站让寻找答案变得非常容易。请将这些与坚持不懈的努力相结合。你可以将本书作为你的编程入门书籍。同样她也适用于想要扩展知识的在职程序员。每次在世界各地的演讲中,我都非常感谢 Thinking in Java 这本书给我带来的所有荣誉。事实证明，这些荣誉对我现在的 [Reinventing Business](http://www.reinventing-business.com) 项目中和加强外界与公司的联系是非常宝贵的。最后,写这本书的原因之一是支持我 [Reinventing Business](http://www.reinventing-business.com) 重塑，似乎下一个合乎逻辑的步骤是实际创建一个所谓的蓝绿色组织（Teal Organization）。我希望这本书可以成为该项目的一种众筹。


## 教学目标

每章教授一个或一组相关的概念，并且这些知识不依赖于尚未学习到的章节。这样以来，学习者可以在当前知识的背景框架下循序渐进地掌握 Java。

本书的教学目标：


1. 循序渐进地呈现学习内容，以便于你在不依赖后置知识框架的情况下轻松完成现有的学习任务，同时尽量保证前面章节的内容在后面的学习中得到运用。如果确有必要引入我们还没学习到的知识概念，我会做个简短地介绍。

2. 尽可能地使用简单和简短的示例，方便读者理解。而不强求引入解决实际问题的例子。因为我发现，相比解决某个实际问题，读者更乐于看到自己真正理解了示例的每个细节。或许我会因为这些“玩具示例”而被一些人所诟病，但我更愿意看到我的读者们因此能保持饶有兴趣地学习。

3. 把我知道的以及我认为对于你学习语言很重要的东西都告诉你。我认为信息的重要性是分层次结构的。绝大多数情况下，我们没必要弄清问题的所有本质。好比编程语言中的某些特性和实现细节，95%的程序员都不需要取知道。这些细节除了会加重你的学习成本，还让你更觉得这门语言好复杂。如果你非要考虑这些细节，那么它还会迷惑该代码的阅读者/维护者，所以我主张选择简单的方法解决问题。

4. 希望本书能为你打下坚实的基础，方便你将来学习更难的课程和书籍。



## 语言设计错误

每种语言都有设计错误。当新程序员必须涉足语言特性，并猜测应用场景和使用方式时，他们体验到极大的不确定性和挫折感。承认错误令人尴尬，但这种糟糕的初学者经历比认识到你错了什么还要糟糕。哎，每一种设语言/库的设计错误都会永久地嵌入在 Java 的发行版中。

诺贝尔经济学奖得主约瑟夫·斯蒂格利茨（Joseph Stiglitz）有一套适用于这里的人生哲学，叫做“承诺升级理论”：继续犯错误的成本由别人承担，而承认错误的成本由自己承担。

如果你有读过我过去的作品，那么你应该知道，我一般倾向于指出这些语言设计错误。Java 已经发展出了一批狂热的追随者，他们对待这门语言更像是阵营而不是编程工具。因为我已经写过有关 Java 的书，所以他们理所当然的认为我也是这个“阵营”的一份子。于是，当我指出 Java 的错误时，就会造成两种影响：

1. 最初，会有许多错误“阵营”的人成为了牺牲品。最终，时隔多年，大家都意识到这是个设计上的错误，然后错误就这样成为了 Java 历史的一部分。

2. 更重要的是，新程序员并没有经历过“他们”为什么要采用这种实现方式的斗争过程。特别是那些隐隐约约感觉不对却依然说服自己“我必须要这么做”或者“我只是没学明白”从而继续错下去的人。更糟糕的是，教授这些编程知识的老师们没能深入的去研究这里是否有设计上的错误，而是继续错误的解读。通过了解语言设计上的错误，能让开发者们更好的理解和意识到错误的本质，从而更快地进步。

理解编程语言的设计错误至关重要，甚至影响程序员的开发效率。一些公司在开发过程中会避免使用语言的某些功能特性。表面上看这些“功能特性”很高大上，但是弄不好却可能出现意料之外的错误，影响整个开发进程。

已知的语言设计错误也会给新的一门编程语言的发明提供参考意义。探索一门语言能做什么是很有趣的一件事，而语言设计错误能提醒你哪些“坑”是不能再趟的。多年以来，我一直感觉 Java 的设计者们有点脱离群众的。Java 有些设计错误不免错的太明显，我都怀疑语言设计师们到底是为了用户服务还是出于其他的动机设计了这些功能。Java 语言有许多臭名昭著的设计错误，很可能这也是诱惑所在。我感觉这是对程序员的不尊重。为此我很长时间不想于 Java 有任何瓜葛，很大程度上，这也是我为什么不想碰 Java的原因吧。

现今当我再来看 Java 8 时，我发现与之前有许多不同的地方。Java 语言的设计师们似乎对于语言和用户的态度发生了根本性上的改变。在多年忽视用户投诉之后，许多功能和库已经被语言搞砸了。

新功能的设计与以往有很大不同。掌舵者开始重视程序员的编程经验。新功能最终都在努力使语言变得更好，而不仅仅是停留在快速添加想法而不深入研究它们的含义。有一些新功能实现上非常优雅（至少在 Java 约束下尽可能优雅）。

我猜测可能是一些人离开设计组让他们意识到了这点。我没想到会有这些变化！因为这些原因吧，写这本书的体验要比以往的经历要好得多。Java 8 包含了一系列基础和重要的改进。哎，不过 Java 有严格的“向后兼容”承诺。所以可能我们不大可能看到戏剧性的变化，当然我希望我是错的。尽管如此，我很赞赏那些敢于自我颠覆，并为 Java 设定更好路线的人。第一次，对于自己所写的部分 Java 8 代码我终于可以说“我喜欢这个！”

最后，本书所著时间似乎也很不错，因为 Java 8 引入的新功能已经强烈的影响了今后 Java 的编码方式。截止我在写这本书时，Java 9 似乎更专注于对语言底层的基础结构功能的重要更新，但是这些并不会影响本书所关注的编码类型。话说回来，得益于电子书出版形式的便捷，如果我发现本书有需要更新或添加的内容，我可以很快将新版本推送给现有读者。



## 测试用例

本书中的代码示例基于 Java 8 和 Gradle 编译构建，并且这些代码示例都保存在[这个自由访问的GitHub的仓库](https://github.com/BruceEckel/OnJava8-Examples) 中。我们需要内置的测试框架在每次构建系统时运行，否则你将无法保证自己代码的可靠性。为了在本书中实现这一点，我创建了一个测试系统来显示和验证大多数示例的输出结果。这个输出结果我会附加在示例结尾的代码块中。有时仅显示必要的那几行或者首尾行。利用这种方式来改善读者的阅读和学习体验，同时也提供了一种验证示例正确性的方法。



## 普及性

Java 的普及性对于其受欢迎程度有重要意义。学习 Java 会让你更容易找到工作。相关的培训材料，课程和其他可用的学习资源也很多。对于企业来说，招聘 Java 程序员也相对容易。如果你不喜欢 Java 语言，那么最好不要拿他当作你谋生的工具，因为这种生活体验并不好。作为一家公司，在技术选型前一定不要单单只考虑 Java 程序员好招。每种语言都有其适用的范围，有可能你们的业务更适用于另一种编程语言来达到事半功倍的效果。如果你真的喜欢 Java，那么欢迎你。希望这本书能丰富你的编程经验！



## 关于安卓

这本书基于 Java 8 版本。如果你是 Andriod 程序员，请务必学习 Java 5。在《On Java 8》出版的时候，我的另一本基于 Java 5 的著作 Thinking in Java 4th Edition（《Java编程思想》第四版）已经可以在[www.OnJava8.com](http://www.OnJava8.com)上免费下载了。此外，还有许多其他专用于 Andriod 编程的资源。




## 电子版权声明

《On Java 8》仅提供电子版，并且仅通过 [www.OnJava8.com](http://www.OnJava8.com) 提供。任何未经  <mindviewinc@gmail.com>  授权的其他来源或流传送机构都是非法的。本作品受版权保护！未经许可，请勿通过以任何方式分享或发布。您可以使用这些示例进行教学，只要不对本书非法重新出版。有关完整详细信息，请参阅示例分发中的 Copyright.txt 文件。对于视觉障碍者，电子版本有可搜索性，字体大小调整或文本到语音等诸多好处。

任何购买这本书的读者，还需要一台计算机来运行和写作代码。另外电子版在计算机上和移动设备上的显示效果俱佳，推荐使用平板设备阅读。相比购买传统纸质版的价格，平板电脑价格都足够便宜。在床上阅读电子版比看这样一本厚厚的实体书要方便得多。起初你可能会有些不习惯，但我相信很快你就会发现它带来的优点远胜过不适。我已经走过这个阶段，Google Play 图书的浏览器阅读体验非常好，包括在 Linux 和 iOS 设备上。作为一次尝试，我决定尝试通过 Google 图书进行出版。

**注意**：在撰写本文时，通过 Google Play 图书网络浏览器应用阅读图书虽然可以忍受，但体验还是有点差强人意，我强烈推荐读者们使用平板电脑来阅读。




## 版本说明

本书采用 Pandoc 风格的 Markdown 编写，使用 Pandoc 生成 ePub v3 格式。

正文字体为 Georgia，标题字体为 Verdana。 代码字体使用的 Ubuntu Mono，因为它特别紧凑，单行能容纳更多的代码。 我选择将代码内联（而不是将列表放入图像，因为我看过一些书籍），因为对我来说让读者能够在调整正文字体大小时，代码块也可自适应调整的功能非常重要（否则，买电子版，还图什么呢？）。

本书的提取，编译和测试代码示例的构建过程都是自动化的。所有自动化操作都是通过我在 Python 3中编写的程序来实现的。




## 封面设计

《On Java 8》的封面通过 W.P.A.（Works Progress Administration 1935年至1943年美国大萧条期间的一个巨大项目，它使数百万失业人员重新就业）的马赛克创作的（WPA，这是）。它还让我想起了绿野仙踪（The Wizard of Oz）系列丛书中的插图。 我的好朋友、设计师丹尼尔威尔哈里斯（[www.will-harris.com](http://www.will-harris.com)）和我都喜欢这个形象。




## 感谢的人

感谢 Domain-Driven Design（《领域驱动设计》 ）的作者 Eric Evans 建议书名，以及其他新闻组校对帮助。

感谢 James Ward 为我开始使用 Gradle 工具构建这本书，以及他多年来的帮助和友谊。

感谢 Ben Muschko 构建文件的抛光工作，还有感谢 Hans Dockter 给 Ben 这个时间。

感谢 Jeremy Cerise 和 Bill Frasure 来到开发商务虚会预订，并随后提供了宝贵的帮助。

感谢所有花时间和精力来 Crested Butte, Colorado（科罗拉多州克雷斯特德比特）镇参加我的研讨会，开发商务聚会和其他活动的人！你们的贡献可能没被轻易看到，但它非常重要！




## 献礼

> 谨以此书献给我敬爱的父亲 E. Wayne Eckel。
> 1924年4月1日至2016年11月23日

<!-- 分页 -->
<div style="page-break-after: always;"></div>
