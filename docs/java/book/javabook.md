# Java工程师修炼之道 - 梳理Java知识体系

《Java工程师修炼之道》
--

<img src="img/book.png" width="180"/>

- [书籍](book)
- [代码](source)
- [勘误](https://github.com/superhj1987/pragmatic-java-engineer/wiki/Mistakes)

**已开源章节**

> - [1.1 后端基础设施](book/chapter1-servertech/server-basic.md)
> - [1.2 Java后端技术概览](book/chapter1-servertech/server-tech-tree.md)
> - [1.3 如何学习后端技术](book/chapter1-servertech/how-to-study.md)
> - [2.1 项目构建](book/chapter2-project/build.md)
> - [2.2 代码版本控制](book/chapter2-project/vcs.md)
> - [2.3 代码质量保证](book/chapter2-project/quality.md)
> - [8.1 调优准备](book/chapter8-profile/ready.md)
> - [附录A: 代码构建常用命令](book/appendix/build-cmd.md)
> - [附录B: Git常用命令](book/appendix/git-usage.md)
> - [附录E: Java调优常用命令](book/appendix/java-profile.md)
> - [附录F 如何应对在线故障](book/appendix/online-debug.md)
> - [附录G 架构简明指南](book/appendix/arch-usage.md)

[**购买链接**](https://item.jd.com/12325207.html)

### 后续计划

> 此书一开始是计划有一章专门讲述大数据开发技术，毕竟现在越来越多的公司在构建自己的大数据平台，大数据技术也逐渐成了Java工程师的必备技能。但自己此方面经验较少，自认并没有达到可以向别人输出知识的程度，于是暂时搁置此部分。

逐步把部分内容开源在此项目中，并补充一些新的内容进来。

- Zookeepr本来是想放在大数据一章，现在会作为数据存储的一节补充进来。
- 异步响应式Web框架会补充在开发框架一章，以Vert.x为主，Spring Flux为辅。
- Redis加入新版本的特性，并补充如何使用Redis实现分布式锁。
- Kafka加入最新版本的特性，尤其是Kafka Streams和Exactly one语义。
- Elasticsearch基于5.0版本更新。
- 补充协程到并发编程中。
- 补充Netty到网络编程中。
- 使用Hystrix做资源隔离和限流会补充在Java开发利器中。
- 补充RxJava的使用在Java开发利器中。
- 补充Java10和Kotlin的部分到Java新版本特性。

**也欢迎大家提交内容，以丰富此书。^_^**

### 内容介绍

见 [**前言**](book/README.md)

### 推荐

>2013年，我和本书作者的接触是从基于网易的一个大型互联网应用合作开始的，我见证了从第一行代码到整个系统服务于亿级用户的过程，并且相信这种经历对开发者来说是一笔巨大的财富，其中大量的开发和实战经验都会在本书中得到充分的体现，相信读者能从书中直接领略到丰富的实战知识。在与本书作者的合作过程中，其对Java技术的热爱与追求孜孜不倦，对问题刨根问底，直到理解透彻、灵活应用，这些都令我印象深刻。这些年，我与本书作者一直保持沟通交流、相互学习，他将近十年的实战经验沉底于本书以实现对后端技术的探索、布道，非常值得开发者与近高窗卧听秋。
>
>后端技术涉及内容非常广泛，Java语言也是互联网开发行业使用的主流语言，相信后续也将继续流行很长一段时间，而本书作者也一直从事Java后端开发工作。在本书中作者比较系统地从总体上描述了后端技术相关的理论知识，包括基础设施、网关服务及框架选型等基本原则，然后以实际经验进行示例说明，接着详细梳理了Java的后端技术，相信读者读完本书后会更全面地理解后端技术。互联网的业务建设需要不同角色的开发者共同协作完成，因此，系统工程化是开发者首先要共同遵守的规范或约定，包括代码规范、版本管理和代码质量检查等。
>
>开发框架的选型进一步地为工程化提供了基础，也能加速推进互联网开发，尽管是否重复造轮子是一个恒久的话题，但是没有永远的银弹，只要在合适的时间里根据团队的能力选择合适的技术框架就好。一般来讲，目前常用的框架包括基本的依赖注入、AOP、事务管理、连接池管理、数据操作、日志服务等，在众多的框架中，本书作者选用目前在Java领域使用最广泛的Spring做深入的分析，详细地说明各组件的基础知识、基本原理和实际使用案例，最难得的是把较多开发者遇到的坑都用真实的示例进行了说明，可以帮助开发者快速地跳过这些伤心地带，同时也把最佳实践画龙点睛地带给开发者。
>
>数据存储无疑是所有系统应用中非常重要的一环，应用的场景用例也和数据库的选型有极其重要的关系，开发者选择关系型数据库还是非关系型数据库是需要根据软件成本与人力成本来进行权衡的，比如是选择MySQL、Oracle等开源或商业的数据库。本书重点从数据库的基础知识、索引和表优化等方面以详尽的示例为更好地选择数据库的存储类型提供了更多的知识。

>早期的关系型数据库一般能满足数据达到一定规模的企业的需求，而在互联网业务领域，特别是移动互联网领域内的元数据或者日志数据等，达到亿数量级别是很常见的，这时通常使用非关系型数据库，在非关系型数据库里使用非常多的有MongoDB、HBase等分布式数据库系统。作者在自身的企业开发实践中，得到了大量的使用经验和最佳实践。为了加速后端应用，缓存热数据是加速业务、提高业务性能、提升用户体验的重要手段，通过使用本地缓存、远程缓存进行数据加速、数据预热或提高数据的命中率，是开发者在应用开发的过程中常会遇到的场景。
>
>“路漫漫其修远兮，吾将上下而求索”，后端技术每年都在不断发展，所用技术也有变化，近些年Java语言的发展速度不那么快了，但是总体是在不断前进发展的，本书作者带领的团队一直深耕此领域并希望通过本书为技术开发人员带来更多帮助。 
>
>-- **尧飘海，网易云基础服务（蜂巢）首席架构师**

---

>Hey！新来的读者，为了吸引你的注意力我真是煞费苦心，但最终还是没能写出一句特别吸引眼球的话来，毕竟写序的我不是标题党出生。此刻我真的非常能理解你拿到新书之后那渴望知识的心情，所以你恨不得一个字的“序”也不要看到，直接到达“最有价值”的知识点。但作为一名资深转业码农（对！你没看错，是“转业”，不是“专业”）还是想说一句，你先看完序，5分钟后到达知识的战场，会更稳！
>
>相信你已经在看“序”了，那么我们来说点正经事。
>
>你的知识体系的养成有3个关键阶段：看山是山、看山不是山、看山还是山。本书的适用人群是“看山不是山”的那些人，如果你恰好处于这个阶段，恭喜你！书钱没白花。
>
>Java是一门非常容易入门的语言，初学者经过初期的学习之后基本能掌握DEMO级别的编程应用。相信读者你已经度过了这个阶段，但是Java庞大的体系可能会把你绕晕，又或者你还没看到Java的生态系统有多么复杂。此时，你需要本书。从事程序员这个工作，到比较高阶的时候，其实是不挑语言的，语言只是工具，而你可以在纷繁复杂中游刃有余。但几乎每一位高手都是先深入一个领域，再横向发展的。你可以不用着急后续的横向发展，先坚定自己学习Java的信心！因为，从广泛的应用场景、顶级的开源生态、未来可期的薪水和职位来说，Java都是非常不错的选择。
>
>敲黑板，画重点！下面来解释一下，为什么本书面向的是“看山不是山”的人群。在度过Java的入门期之后，会有一个烦恼，那就是面对Java这么庞大的体系，我们究竟应该学习什么？选择方向，往往比努力更重要！是使用J2SE编写桌面程序？是使用J2ME编写嵌入式应用？还是使用J2EE编写企业级应用？这些是我们那个泛黄的年代特有的烦恼。而现在的烦恼可能是学Android？还是学Java后端？即便大方向你已经十分坚定，而且选择了Java后端编程，但因为复杂的知识体系和Google发布的各种教程文档，眼前看到的已经不再是清晰的山脉，而是一片迷雾。此时，你需要本书，因为它给你指明了努力的方向。
>
>本书的结构、阐述的方式和大部分的“指南”书籍有较大的区别，本书是以笔记和要点的形式进行呈现的，用现在的话说就是捞干货。本书涵盖的知识，是以现代工程实践中的实际案例出发来组织的，所以知识点范围非常广泛，每一个点都对最关键的“Best Practice”简明扼要地进行了说明。你在阅读本书的时候需要一些相关经验，不然无法跟上作者的节奏，建议在有一定的知识准备后再阅读本书，这样你会受益匪浅。从另外一个角度看，在你有了一定的基础积累之后，本书可以帮助你全面地了解一个现代化的最先进的工程实践是怎样的。本书讲述了目前行业中最常用的，经过了实践的工程方案，这将是你快速进阶的最佳指引。 
>
>-- **孙建，随身云（中华万年历）联合创始人&CEO**

---

>扎实的基础理论知识是内功底子，丰富的实践经验是招式。如本书作者所说，精妙的招式决定了你的武功下限，而深厚的内功底蕴会承载你所能企及的高度。那么，在后端技术栈中，内功与招式之间如何去关联起来，本书作者以其多年的钻研与实践结合心得，通过本书为你一一梳理。 
>
>-- **阙杭宁，网易云信CTO**

---

>作者是一位技术人,有多年的Java技术积累,是极少数真正热爱技术的人。在随身云架构师的工作让他有机会站在更高的层次进行系统架构的工作,这些实践经验和平时感悟都沉淀在作者的著作和博客中,相信每位Java工程师都能从中获取帮助。
>
>-- **秦绪震，十露盘科技联合创始人，技术负责人**

---

>本书作者根据自身多年的JAVA后台开发经验, 提纲挈领的总结JAVA后台开发的各个关键技术点，这些知识点都是一个合格的JAVA工程师必须掌握的技能。它既可以作为新人的技术学习指南，也可以帮助老手对于自己的知识面进行查漏补缺，是一本非常好的技术指南。 
>
>-- **饶洵（蜚天），阿里巴巴技术专家**

---

>作为一个在后端摸爬多年的Java开发工程师，这本书让我温故而知新。书中介绍的Java相关的知识技能树，不仅涵盖了我个人多年的Java开发技术知识点，也对我所陌生的一些知识点进行了详解，让我突然有一种继续学习的冲动。
>
>一个Java开发工程师的成长，不仅要对Java语言及其特性有深层次的理解，也需要掌握与Java相关的框架、生态及后端开发知识。这本书正是将后端开发工程师需要掌握的技能做了总结，对于提高开发技能有很好的指导作用。
>
>我推荐这本书，对于具有一定Java基础和后端开发知识的读者来说，该书不仅具有仔细学习的价值，同时也是一本可以经常翻阅的工具书籍，对于Java开发工程师的成长和进阶有很大的指导作用。
>
> 一本好的技术书籍，不仅要仔细阅读、学习理解，还需要进行较多的实践，将所看所学进行应用，通过不断地实践，加深知识点印象，从而形成永久的记忆和技能。希望各位读者能够通过掌握书中的知识和技能，逐步成长为技术骨干和专家，从而创造更多的技术输出、产品输出，创造更多的财富。 
>
> -- **张小川，网易考拉海购架构师，供应链技术主管**