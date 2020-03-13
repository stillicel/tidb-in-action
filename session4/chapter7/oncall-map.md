### TiDB 集群问题导图的起源
在使用 TiDB 的过程中，用户总会遇到不同的问题，解决这些问题的通常做法是根据报错或者现象，去 TiDB 官网查询文档以及 FAQ，或者在 askTUG 网站上发帖子寻求帮助。但 PingCAP 官方经常处理用户各种各样的问题，积累下来了很多处理问题的经验，那么有没有一种方式，可以让用户自助的根据报错及现象，利用官方内部积累的经验，能快速定位和解决一些常见问题的方法呢？并且针对各个模块的问题用户有没有方法快速有一个系统化的了解？并且以上需要有很低的学习成本，容易理解。

答案是肯定的，为了达到上面提到的目标，PingCAP 把一些常见问题的现象、原因、解决办法以及涉及到的版本归纳总结到一张思维导图中，我们叫做 diagnose-map。用户可以参考导图来快速定位和解决自己遇到的问题。其中包括了 7 大系列的几十中常见问题，并且还在逐步补充中。

### 获取问题导图的方式
可以在 https://github.com/pingcap/tidb-map/blob/master/maps/diagnose-map.png 来下载 TiDB 集群问题导图。该 png 图片是通过思维导图工具把 markdown 格式的 https://github.com/pingcap/tidb-map/blob/master/maps/diagnose-map.md 转换而来的。

### 问题导图的使用
TiDB 集群问题导图是一个思维导图，汇集了各个模块常见的一些问题。 该导图中把各个模块的问题进行了分类，比如把引起 TiKV OOM 问题的一些潜在原因以及解决方案放在一起，把导致 PD 选举问题的一些潜在原因和解决办法放在一起等等。另外也把两种常见的现象，服务不可用和 latency 明显增高作为两个单独的分支，用户可以从这两个分支出发寻找潜在的问题。举个例子，比如客户端收到 region is unavailable 错误，1.1.1 解释了导致该错误的原理是怎样的，然后列举了 4 种可能导致该问题的原因，用户可以根据自己集群的现象对号入座，按照流程来分析和解决自己遇到的问题。

另外可以看到一些类似 ONCALL-958 的东西，是该问题的处理案例，经过抽象后发布在该项目中 https://github.com/pingcap/tidb-map/tree/master/maps/diagnose-case-study。

### 问题反馈
由于 TiDB 一直在快速迭代中，该导图不可能把所有可能的问题都提前列出来，只能是一点点完善，如果在该导图中找不到答案的问题可以搜索官方文档或者在 askTUG 上发帖子询问。

另外在使用 TiDB 集群问题导图的过程中如果有遇到任何问题，或者对于改进该导图有自己的建议，或者导图中一些信息是错误的，欢迎给 https://github.com/pingcap/tidb-map 提 issue。
