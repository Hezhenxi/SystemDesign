# 系统设计与优化&amp;DDIA :see_no_evil:
## 目录

<a name="3060-1621846615933"></a><a name="uiay-1699845707467"></a>[一.数据库设计](#jeyl-1677787446995)

<a name="objj-1699845707469"></a>[1. 关系型数据库](#5hya-1677787446996)

<a name="zdzw-1699845707471"></a>[.E-R图，由台湾工程师提出的设计概念](#ohc5-1621692571287)

<a name="suuh-1699845707473"></a>[.流程图-业务逻辑相关，系统用户动作。抽象出E-R图](#5ocb-1645598528868)

<a name="pzzm-1699845707476"></a>[1.1 E-R图 ](#gzqe-1677787446997)

<a name="ljlv-1699845707478"></a>[1.根据名词抽象出实体](#r1ac-1621692724628)

<a name="64w9-1699845707480"></a>[2.名词找属性](#d2fl-1621692745600)

<a name="n7iq-1699845707482"></a>[3.实体间联系](#dwkp-1621692752824)

<a name="hmrx-1699845707484"></a>[1.2 转化成数据库设计（公式）](#c2cy-1677787446998)

<a name="u7lg-1699845707486"></a>[.1 对1 关系 往记录少的乙方加主键](#xmox-1621692858500)

<a name="8o7q-1699845707488"></a>[.1对n 关系 ，往 n 实体加关联主键 ](#mdr8-1621692924289)

<a name="qeef-1699845707490"></a>[. n对 m 关系，需要一个关联表作映射关联](#hd3i-1621692960576)

<a name="4onf-1699845707492"></a>[二.系统优化](#cdso-1677787447000)

<a name="j3l3-1699845707494"></a>[整体的优化](#3qep-1642647362896)

<a name="2q8i-1699845707496"></a>[-cpu -> 纳秒级别](#knge-1642647371136)

<a name="inat-1699845707498"></a>[-内存RAM（GB）/高速缓存(KB) -> 微秒级别(分级缓存)](#1xur-1642647384168)

<a name="hcco-1699845707500"></a>[-磁盘（TB）-> 毫秒级别(减少io次数,减少随机io-redolog)   ](#ziti-1642647439005)

<a name="uw2o-1699845707502"></a>[-网络传输/系统交互 -> 秒级 (减少io，连接池化)                                        ](#irbp-1642647458856)

<a name="5ljq-1699845707504"></a>[1.分控系统优化复盘](#tncv-1677787447001)

<a name="lphx-1699845707506"></a>[1.1 数据库系统](#ydq7-1677787447002)

<a name="8b19-1699845707508"></a>[1.2 sql慢](#wxdd-1677787447003)

<a name="9fh5-1699845707510"></a>[1.3 接口慢](#olpb-1677787447004)

<a name="27yk-1699845707512"></a>[===数据密集型应用===](#rpxb-1677787447005)

<a name="nyk3-1699845707514"></a>[设计数据密集型应用](#unbe-1677787447006)

<a name="nbf3-1699845707516"></a>[1.可靠性、可拓展性、可维护性能](#kwfx-1677787447007)

<a name="fopr-1699845707518"></a>[-功能性需求：CRUD](#lykw-1644227240038)

<a name="shog-1699845707520"></a>[-非功能性需求：安全性，可靠性，合规性，可扩展性，兼容性和可维护性](#b2tu-1644227249556)

<a name="tdzi-1699845707522"></a>[.可靠性：](#qqm5-1644227303238)

<a name="azco-1699845707524"></a>[.可扩展性： ](#7xms-1644228225080)

<a name="egrd-1699845707526"></a>[.可维护性：   ](#elzq-1644228563046)

<a name="fzqr-1699845707528"></a>[2.数据模型与查询语言](#jufm-1677787447008)

<a name="bbij-1699845707530"></a>[-关系模型](#pgu6-1699844351041)

<a name="gjpo-1699845707532"></a>[-NoSql (es,redis)](#kfpd-1644410618294)

<a name="gyew-1699845707534"></a>[1.文档数据库：](#0p23-1644410807294)

<a name="idvd-1699845707536"></a>[  2.图形数据库 ：](#09bl-1644410666587)

<a name="hisk-1699845707538"></a>[-其它模型(基因序列)](#6fxw-1644410924417)

<a name="e3yf-1699845707540"></a>[3.存储与检索](#sm0u-1677787447009)

<a name="loaa-1699845707542"></a>[-优化事务处理（OLTP）transaction ](#bhcv-1644935436804)

<a name="zhek-1699845707544"></a>[1.OLTP系统通常面向用户，大量的请求。](#tbhw-1699844517372)

<a name="nsxl-1699845707546"></a>[2.磁盘寻道时间往往是这里的瓶颈。](#fnev-1644935714127)

<a name="7gxc-1699845707548"></a>[3.应用程序使用某种键来请求记录，存储引擎使用索引来查找所请求额键的数据。](#cjwp-1644935609899)

<a name="p4vy-1699845707550"></a>[-优化分析（OLAP）analys](#jg7s-1699844443567)

<a name="qvnp-1699845707552"></a>[-OLTP两大主流学派的存储引擎：](#8sgm-1644935924013)

<a name="6que-1699845707554"></a>[1.日志结构学派](#i55y-1644935943748)

<a name="eobt-1699845707556"></a>[2.就地更新学派](#h3il-1644935977285)

<a name="hjog-1699845707558"></a>[4.编码（序列化）与演化(XML,JSON,CSV)](#lbs1-1677787447010)

<a name="nz9b-1699845707560"></a>[分布式系统](#d4ge-1677787447011)

<a name="wgnq-1699845707562"></a>[4.分布式数据](#4p9n-1677787447012)

<a name="zovr-1699845707565"></a>[1.高可用性](#o4ag-1646310813851)

<a name="16xl-1699845707567"></a>[2.断开连接的操作](#snwm-1646310894841)

<a name="ww92-1699845707569"></a>[3.减少延迟(节点近)](#evly-1646310918322)

<a name="behc-1699845707571"></a>[4.可拓展性](#itsh-1646310968967)

<a name="dboe-1699845707573"></a>[-复制的三种主要方法：](#gbgq-1646311175182)

<a name="m8rz-1699845707575"></a>[1.单主复制](#wg6v-1646311185918)

<a name="whlq-1699845707577"></a>[2.多主复制](#ftqb-1646311200843)

<a name="5rxq-1699845707579"></a>[3.无主复制](#4xbf-1646311410600)

<a name="wxtr-1699845707581"></a>[-一致性模型：](#nlnz-1699845075606)

<a name="4cly-1699845707583"></a>[1.写后读](#anqq-1646312272172)

<a name="oywj-1699845707585"></a>[2.单调读](#hedn-1646312288296)

<a name="d94z-1699845707587"></a>[3.一致前缀读](#fizh-1646312291911)



<a name="jeyl-1677787446995"></a>**一.数据库设计**

<a name="5hya-1677787446996"></a>**1. 关系型数据库**

<a name="ohc5-1621692571287"></a>**.E-R图，由台湾工程师提出的设计概念**

<a name="4z7m-1645598900270"></a>权益系统数据库设计复盘：雄爷并行看需求文档一两天设计DB。

<a name="5ocb-1645598528868"></a>**.流程图-业务逻辑相关，系统用户动作。抽象出E-R图**

<a name="gzqe-1677787446997"></a>**1.1 E-R图** 

<a name="r1ac-1621692724628"></a>**1.根据名词抽象出实体**

<a name="d2fl-1621692745600"></a>**2.名词找属性**

<a name="dwkp-1621692752824"></a>**3.实体间联系**

<a name="cyqi-1699843717785"></a>（单条记录对应关系 A表一条记录对应B表多条记录，B表一条记录对应A表多条记录即 m对）

<a name="53bo-1621692829033"></a><a name="c2cy-1677787446998"></a>**1.2 转化成数据库设计（公式）**

<a name="xmox-1621692858500"></a>**.1 对1 关系 往记录少的乙方加主键**

<a name="mdr8-1621692924289"></a>**.1对n 关系 ，往 n 实体加关联主键** 

<a name="hd3i-1621692960576"></a>**. n对 m 关系，需要一个关联表作映射关联**

<a name="p0tb-1655431896857"></a><a name="i6pd-1655431897042"></a>最好不要自己设计自己的表，关乎字段名统一（属性思想上的统一），以及字段冗余，字段依赖问题。

<a name="8iuc-1649150300481"></a><a name="cdso-1677787447000"></a>**二.系统优化**

<a name="3qep-1642647362896"></a>**整体的优化**

<a name="knge-1642647371136"></a>**-cpu -> 纳秒级别**

<a name="1xur-1642647384168"></a>**-内存RAM（GB）/高速缓存(KB) -> 微秒级别(分级缓存)**

<a name="glib-1699843869066"></a>          redis缓存

<a name="ziti-1642647439005"></a>**-磁盘（TB）-> 毫秒级别(减少io次数,减少随机io-redolog)**   

<a name="e1bq-1699843762732"></a>减少io(磁盘读写):sql索引       ----数据存储一般在DB系统中

<a name="irbp-1642647458856"></a>**-网络传输/系统交互 -> 秒级 (减少io，连接池化)**                                        

<a name="yp7k-1699843769117"></a>减少io(系统交互/连接池连接数)：去除for循环sql  ，CDN,   --池化思想，创建和销毁消耗大的资源创建一个资源池，维护一定数量的资源数，统一管理资源创建和销毁

<a name="six7-1642647372926"></a><a name="tncv-1677787447001"></a>**1.分控系统优化复盘**

<a name="ydq7-1677787447002"></a>**1.1 数据库系统**

<a name="xsbg-1642647218571"></a>数据库的性能过低

<a name="eg0t-1642647223498"></a>提升硬件配置

<a name="wxdd-1677787447003"></a>**1.2 sql慢**

<a name="javd-1642647045138"></a>数据量大一千6百多万条数据

<a name="no1c-1642647140123"></a>删除冗余数据，每天采集13次，需求7天外数据只保留最新一批数据，修正删除的sql, 剩余数据，200w~600w左右。

<a name="ykot-1642649009232"></a>添加索引

<a name="olpb-1677787447004"></a>**1.3 接口慢**

<a name="blpq-1642649142995"></a>for循环遍历sql

<a name="s2zh-1642649153917"></a>去除for循环sql

<a name="yryq-1642649204976"></a> 频繁的采集种erverywhere log.info

<a name="afeg-1642649254648"></a>减少日志文件io，非必要信息改为debug。

<a name="fjt3-1643394063817"></a><a name="efqc-1643394063942"></a>优先考虑优化代价比较少的代码优化及sql优化，完成此类优化再考虑系统设计层面的优化，如：分库分表等（系统复杂度提升）。

<a name="navz-1652597408993"></a>一期历史数据重大bug修复方案设计问题（参看文档）： 注意像算法那样考虑极端情况（bug）处理，梳理方案的优缺点，对比不同方案实现优缺点接受度。

<a name="w6cm-1652597504660"></a>1.保证数据为最新的一批：

<a name="o4ka-1652597649729"></a>原方案. 每天13批次数据，不做事务回滚，取maxid ，>24小时数据删除---<24小时当天取消航班会在其中

<a name="ihuw-1652599412442"></a>配置难点：采集时段不同，每个账号采集不同天数; 采集的时间频率不同：

<a name="uarz-1652598784895"></a>熊爷方案：不改动原有逻辑，增加字段增加判段历史数据逻辑。

<a name="yxwj-1652599128439"></a>优点：基本不用改动一期代码和逻辑，改动sql增加判断历史条件。

<a name="rjdk-1652599326567"></a>缺点：新增判断的逻辑需要批次保证事务性，且配置难度很大，跨小时频率或者地区重叠，不可保证批次完整性，对比无效且配置和代码都得写死。

<a name="cehv-1652599093885"></a>我的方案：保证批次完整性，失败的批次直接整批删除，取最新一批。也是仅改动sql，获取最新一批批次代替 max(id)。

<a name="fm9n-1652599202701"></a>优点：只需要天数不重叠即可，配置相对灵活。

<a name="0ckh-1652599307805"></a>缺点：需要改sql逻辑，业务逻辑影响风险较大，需仔细验证。

<a name="nwww-1652597653246"></a> 

<a name="yjau-1644231171609"></a>分控系统重构设计

<a name="q9y5-1644231078993"></a>可靠性：写操作频繁，250k/h ~70次请求/s，将采集和后台分开两个应用。目前问题，采集两周左右系统资源耗尽会挂，可有多台服务器，实际上只用了两台。（集成应用监控，实现预警）

<a name="1ozg-1644231149674"></a>可拓展性：暂无,用户负载暂无数据(涉及到集群那就得分布式锁了)

<a name="nbg9-1644231153386"></a>可维护性：代码质量，可读性。

<a name="wrwk-1642647280506"></a><a name="rpxb-1677787447005"></a>**===数据密集型应用===**

<a name="ef5t-1644230945318"></a>数据系统基础

<a name="unbe-1677787447006"></a>**设计数据密集型应用**

<a name="kwfx-1677787447007"></a>**1.可靠性、可拓展性、可维护性能**

<a name="zrzj-1642646974315"></a>小结：一个应用必须满足各种需求才称得上有用

<a name="lykw-1644227240038"></a>**-功能性需求：CRUD**

<a name="b2tu-1644227249556"></a>**-非功能性需求：安全性，可靠性，合规性，可扩展性，兼容性和可维护性**

<a name="qqm5-1644227303238"></a>**.可靠性：**

<a name="vdpc-1699843965882"></a>以为着即使发生故障，系统也能正常工作。

<a name="mk9e-1644227360160"></a>故障可能发生在硬件（通常是随机和不相关的）

<a name="w7by-1644227387308"></a>软件（通常是系统性的bug,很难处理）

<a name="dozl-1644227415061"></a>人类（不可避免的时不时出错）

<a name="fvz4-1644227444254"></a>**容错技术**可以对终端用户隐藏某些类型的故障。

<a name="7xms-1644228225080"></a>**.可扩展性：** 

<a name="t59j-1699843967201"></a>意味着即使在增加负载的情况下也能保持性能的策略。

<a name="gqfn-1644228379215"></a>为了讨论可拓展性，首先要定量描述负载和性能的方法。

<a name="krij-1644228405843"></a>推特主页时间线的例子，介绍描述负载参数，并将响应时间百分点作为衡量性能的一种方式。头部阻塞、尾部延迟。(有很多人通过将工作负载迁移到低延迟、自适应的GC来控制尾部延迟-infoQ java趋势)

<a name="bynr-1644228470161"></a>在可扩展的系统中可以添加**处理容量** 以在高负载下保持可靠。

<a name="elzq-1644228563046"></a>**.可维护性：**   

<a name="vg1v-1699843968229"></a>可维护性实质上是关于工程师和运维团队生活质量的。

<a name="mq1x-1644231096441"></a>良好的抽象可以帮助降低复杂度，并使系统易于修改和适应新的应用场景。

<a name="qj5f-1644228656997"></a>良好的可操作性意味这对系统的健康状态具有良好的可见性，并拥有有效的管理手段。

<a name="gwsd-1644231020558"></a><a name="jufm-1677787447008"></a>**2.数据模型与查询语言**

<a name="guby-1644404619396"></a>本章小结：数据模型时一个巨大的课题，在本章中，我们快速浏览了各种不同的模型。以便激起兴趣，更多的了解**最适合你的应用的需求模型**。（数据库选型）

<a name="o6we-1644404838474"></a>在历史上，**数据最开始被表示为一颗大树（层次型结构**），但是这不利于表示多对多的关系，所以发明了

<a name="pgu6-1699844351041"></a>**-关系模型**

<a name="jayo-1699844352979"></a>来解决这个问题。

<a name="kfpd-1644410618294"></a>**-NoSql (es,redis)**

<a name="uzbw-1699844301003"></a>**通常**不会为存储的数据强制一个模式，这可以使应用程序更容易适应不断变化的需求。

<a name="0p23-1644410807294"></a>**1.文档数据库：**

<a name="9rlb-1699844336493"></a>数据通常是自我包含的，而且文档之间的关系非常稀少

<a name="09bl-1644410666587"></a>  **2.图形数据库 ：**

<a name="imif-1699844337670"></a>与文档数据库相反的场景-任意事务都可能与任何事务相关联

<a name="6fxw-1644410924417"></a>**-其它模型(基因序列)**

<a name="he0m-1699844309707"></a>** 基因组 通常需要 **序列相似性搜索，意味着一**个很长的字符串，并在一个拥有类似但不完全相同的字符串的大型数据库中寻找匹配。这里所描述的数据库都不能处理这种用法。研究人员编写了想GenBank专门的基因组数据库软件。

<a name="opsf-1644411138194"></a>                 粒子物理学家进行大数据类型的大规模数据分析。粒子对撞机（LHC）这样的项目可以工作在数百亿兆字节的范围内。这样的规模下，需要指定解决方案来阻止硬件成本的失控。

<a name="pnul-1644935322505"></a><a name="sm0u-1677787447009"></a>**3.存储与检索**

<a name="ycte-1644935336049"></a>本章小结：数据库如何处理存储何检索。将数据存储在数据库中会发生什么，再次查询数据库会发生什么？

<a name="bivs-1644935398311"></a>在高层次上，存储引擎分两大类：

<a name="bhcv-1644935436804"></a>**-优化事务处理（OLTP）transaction** 

<a name="tbhw-1699844517372"></a>**1.OLTP系统通常面向用户，大量的请求。**

<a name="fnev-1644935714127"></a>**2.磁盘寻道时间往往是这里的瓶颈。**

<a name="cjwp-1644935609899"></a>**3.应用程序使用某种键来请求记录，存储引擎使用索引来查找所请求额键的数据。**

<a name="jg7s-1699844443567"></a>**-优化分析（OLAP）analys**

<a name="n8me-1644935726822"></a>    OLTP数据 copy and translatin 转换为适合业务分析的数据副本 to 数据仓库（OLAP）

<a name="3cwp-1644935731444"></a>OLAP**数据仓库**和类似的分析系统不太知名，因为只要由业务分析人员使用，而不是由最终用户使用

<a name="s6pt-1644935799372"></a>处理比OLTP系统少得多得查询量，但是每个查询通常要求很高，短时间内扫描百万条记录。

<a name="cyhe-1644935862917"></a>磁盘带宽（不是查找时间）往往是瓶颈，列式存储是这种工作负载的流行解决方案。

<a name="8sgm-1644935924013"></a>**-OLTP两大主流学派的存储引擎：**

<a name="i55y-1644935943748"></a>**1.日志结构学派**

<a name="4nm8-1644935988277"></a>只允许附加到文件和删除过时文件，但不会更新已经写入的文件。（高效，顺序IO?）

<a name="6ymo-1644936029696"></a>Bitcask, SSTables, LSM树，LevelDB, Cassandra, HBase, Lucene等都属于这个组。

<a name="h3il-1644935977285"></a>**2.就地更新学派**

<a name="2w0c-1644936091115"></a>将磁盘视为一组可以覆盖的固定大小页面。（随机IO?）

<a name="hpzs-1644936142472"></a>B树是这种哲学的最大例子，被用在所有主要的关系数据库中，还有许多非关系数据库。

<a name="fil5-1644936170765"></a><a name="vypn-1644936170925"></a>日志结构的存储引擎是相对较新的发展，他们的主要想法是，系统地将随机访问写入顺序写入磁盘，由于硬盘驱动器和固态硬盘的性能特点，可以实现更高的写入吞吐量。在完成OLTP方面，我们通过一些更复杂的索引结构和为保留所有数据而优化的数据库做了一个简短的介绍。

<a name="a5tj-1644936526197"></a>然后我们从存储引擎的内部绕开，看看典型的数据仓库的高级架构。这一背景说明了为什么分析工作负载和OLTP差别很大：

<a name="nyml-1644936619727"></a>当您的查询需要在大量（几百列）的行中顺序扫描时，索引的相关性就会下降很多。相反，非常紧凑地编码数据变得非常重要，以最大限度地减少查询需要从磁盘读取的数据量。我们讨论了列式存储如何帮助实现这一目标。

<a name="2akd-1644935679338"></a>作为一名应用开发人员，如果您掌握了有关存储引擎内部知识，那么就能更好地那种工具最适合您的特定应用程序。如果需要调整库的参数，这种理解可以让您设想一个更高或者更低的参数可能会产生什么效果。

<a name="ohao-1644936963029"></a>尽管本章不能让你成为一个特定存储引擎的调参专拣，但它至少有大概率使你有了足够的概念与词汇储备去读懂数据库的文档，从而选择合适的数据库。

<a name="en4q-1644936942676"></a><a name="lbs1-1677787447010"></a>**4.编码（序列化）与演化(XML,JSON,CSV)**

<a name="18rw-1644940257792"></a>在本章中，我们研究了将数据结构转换为网络中的字节或磁盘上的字节的几种方法。编码的细节影响其效率，更重要的是应用程序的体系结构和部署它们的选项。

<a name="bfvx-1644940365841"></a>特别是，许多服务需要支持滚动升级（灰度发布），其中新版本的服务逐步部署到少数节点，而不是同时部署到所有节点。滚动升级允许在不停机的情况下发布新版本的服务（从而鼓励在罕见的大型版本上频繁发布小型版本），并使部署风险降低（允许在影响大量用户之前检测并回滚有故障的版本）。这些属性对于可演化性，以及对应用程序进行更改的容易性都是非常有利的。

<a name="w4qv-1644940598057"></a>在滚动升级期间，或出于其它原因，我们必须假设不同的节点正在运行我们的应用程序代码的不同版本。因此，在系统周围流动的所有数据都是以提供向后兼容性（新代码可以读取旧数据-服务端）和向前兼容性（旧代码可以读取新数据-客户端）的方式进行编码是重要的。我们讨论了几种数据编码格式极其兼容性：

<a name="zw4l-1644940805237"></a>编程语言特定编码仅限于单一编程语言，并且往往无法提供向前和向后兼容性。

<a name="1zx9-1644940881501"></a>JSON, XML和CSV等文本格式非常普遍，其兼容性取决于如何使用它们。他们有可选模式语言，这有时是有用的，有时是一个障碍。这些数据格式对于数据类型有些模糊，所以你必须小心数字和二进制字符串。

<a name="q8m7-1644942050475"></a>像Thrift, Protocol Buffers和Avro这样的二进制模式驱动格式允许使用清晰定义的向前和向后兼容性语义进行紧凑，搞笑的编码。这些模式可以用于静态类型语言的文档和代码生成。但是，他们有一个去缺点，就是在数据可读之前需要对数据进行解码。

<a name="hqvm-1644942192088"></a>我们还讨论了几种数据流的几种模式，说明了数据编码是重要的不同场景：

<a name="c94y-1644942236778"></a>数据库，写入数据库的进程对数据进行编码，并从数据库读取进程对其进行解码

<a name="kcmv-1644942289426"></a>RPC 和 REST API, 客户端对请求进行编码，服务器对请求进行解码并对相应进行编码，客户端最终对相应进行解码。

<a name="nvcq-1644942366178"></a>异步消息传递（使用消息代理或参与者），其中节点之间通过发送消息进行通信，消息由发送者编码并由接收者解码。

<a name="oxsf-1644942481249"></a>我们可以小心地得出这样的结论：向前兼容性和滚动升级在某种成都上是可以实现的。愿您的应用程序的演变迅速，敏捷部署。

<a name="rmsh-1646310193756"></a><a name="d4ge-1677787447011"></a>**分布式系统**

<a name="4p9n-1677787447012"></a>**4.分布式数据**

<a name="gr0m-1646310278506"></a>本章考察了复制的问题，复制可以用于几个目的：

<a name="o4ag-1646310813851"></a>**1.高可用性**

<a name="r7ua-1646310833943"></a>即使在一台机器（或多台机器，或整个数据中心）停机的情况下也能保持系统正常运行

<a name="snwm-1646310894841"></a>**2.断开连接的操作**

<a name="x2dq-1646310900787"></a>允许应用程序在网络中断时继续工作

<a name="evly-1646310918322"></a>**3.减少延迟(节点近)**

<a name="iz8f-1646310928916"></a>将数据放置在距离用户较近的地方，以便用户能够更快地与其交互

<a name="itsh-1646310968967"></a>**4.可拓展性**

<a name="ncek-1646310974776"></a>能够处理比单个机器更高的读取量可以通过对副本进行读取来处理

<a name="ybmg-1646311013702"></a><a name="a6ti-1646311014184"></a>尽管是一个简单的目标-在几台机器上保留相同数据的副本，但复制确实一个非常棘手的一个问题。它需要仔细考虑并发和所有可能出错的事情，并处理这些故障的后果。

<a name="cpjg-1646311086181"></a>至少，我们需要处理不可用的节点和网络中断（甚至不考虑更隐蔽的故障，例如由软件错误导致的无提示数据损坏）。

<a name="gbgq-1646311175182"></a>**-复制的三种主要方法：**

<a name="wg6v-1646311185918"></a>**1.单主复制**

<a name="ehug-1646311426407"></a>客户端将所有写入操作发送到单个节点（领导者），该结点将数据更改事件流发送到其它副本（追随者）。

<a name="wgge-1646311567456"></a>读取可以再任何副本中执行，但从追随者读取可能是陈旧的 （最终一致性问题）

<a name="ftqb-1646311200843"></a>**2.多主复制**

<a name="ak8v-1646311613462"></a>客户端发送每个写入到几个领导节点之一，其中任何一个都可以接受写入。领导者将数据更改事件流发送给彼此以及任何跟随着节点。

<a name="4xbf-1646311410600"></a>**3.无主复制**

<a name="b6zn-1646311685371"></a>客户端发送每个写入到几个节点，并从多个节点并行多去，以检测和纠正具有陈旧数据的节点。

<a name="tyus-1646311850435"></a><a name="dzsw-1646311850942"></a>单主复制是非常流行的。多领导和无领导复制可以更加稳健，但以更难以推理并仅提供非常弱的一致性保证为代价。

<a name="sgmj-1646311002454"></a>我们讨论了一些有助于决定应用程序在复制滞后时的行为的

<a name="nlnz-1699845075606"></a>**-一致性模型：**

<a name="anqq-1646312272172"></a>**1.写后读**

<a name="jvwc-1646312310729"></a>用户应该总是看到自己提交的数据。

<a name="hedn-1646312288296"></a>**2.单调读**

<a name="wxgc-1646312331720"></a>用户在一个时间点看到数据后，他们不应该在某个早期时间点看到数据

<a name="fizh-1646312291911"></a>**3.一致前缀读**

<a name="5okd-1646312382954"></a>用户应该将数据视为具有因果意义的状态：例如，按照正确的顺序查看问题及其答复

<a name="drau-1646310922027"></a><a name="eumz-1646312681469"></a>多领导者和无领导者复制方法所固有的并发问题：允许多个写入并发发生冲突。研究了一个数据库可能使用的算法来确定一个操作是否发生在另一个操作之前，或者他们是否同时发生。

<a name="xukg-1646312787143"></a>还谈到了通过合并并发更新来解决冲突的方法。
