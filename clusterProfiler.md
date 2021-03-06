有个拼图的包特别好用
patchwork
https://www.jianshu.com/p/9de9cbff21b9

# GSEA
 
[read://https_zhuanlan.zhihu.com/?url=https%3A%2F%2Fzhuanlan.zhihu.com%2Fp%2F337001292FS](https://zhuanlan.zhihu.com/p/337001292)

GSEA（Gene Set EnrichmentAnalysis），即基因集富集分析，它的基本思想是使用预定义的基因集（通常来自功能注释或先前实验的结果），将基因按照在两类样本中的差异表达程度排序，然后检验预先设定的基因集合是否在这个排序表的顶端或者底端富集。基因集合富集分析检测基因集合而不是单个基因的表达变化，因此可以包含这些细微的表达变化，预期得到更为理想的结果。

GSEA与常说的GO、KEGG pathway分析有何不同？

还是以选秀来说，常用的GO、KEGG pathway提前会对身高做一个阈值设定，低于某个身高的选手直接淘汰，剩下的人按照特长进行富集分类，这样就会将一些有实力的舞者排除在外，好不公平！！那就我们的基因来说，如果从一开始进行了阈值设定，关注少数几个显著上调或下调的基因，这容易遗漏部分差异表达不显著却有重要生物学意义的基因。

那么有人会问，虽然遗漏了一些基因，我们还是可以统计某条通路的上下调基因个数，来判断该通路在实验条件下被抑制或被激活，或者我们直接挑出上调基因和下调基因分别进行富集分析，那么不就得到上调通路和下调通路吗，这里，这样的做法有失偏颇，假如某条通路既有上调基因又有下调基因又该如何解释，另外Fisher精确检验就是想要证明我这个差异基因列表不是随机抽样得到的，而我们事先对差异基因列表的过滤已经对结果的随机性造成了干扰，最后得出的结论其准确性也大大降低。

当然，传统的GO、KEGG pathway也有自己的优势，我们通常求得差异基因列表后，都会在此之上提供给客户Pathway 以及GO 富集分析，毕竟给予成百上千的差异表达基因以简洁、明晰的生物学功能的概括，才是进行高通量生物学表达谱实验的主要目的。

# GO
Gene Ontology（简称GO）是一个国际标准化的基因功能分类体系，提供了一套动态更新的标准词汇表（controlled vocabulary）来全面描述生物体中基因和基因产物的属性。

GO总共有三个ontology（本体），分别描述基因的分子功能（molecular function）、细胞组分（cellular component）、参与的生物过程（biological process）。GO的基本单位是term（词条、节点），每个term都对应一个属性。

**富集的含义：**

每个基因都会对应有一个或多个GO term（也就是GO功能）。

富集涉及到两个概念：前景基因和背景基因。前景基因就是你关注的要重点研究的基因集，背景基因就是所有的基因集。

比如做两个样本对照组和处理组的转录组测序，前景基因就是对照组vs处理组的差异基因，背景基因就是这两组样本的所有表达基因。再比如，我想知道与整个广东省相比，深圳市的大学生是不是显著更多（“大学生”就相当于深圳市民的其中一个GO term）。那么前景就是深圳市的人口，背景就是广东省的人口，每个个体都会有一个标签（如大学生、中学生、小学生等）。

富集的意思就是，某个GO term在所关注的前景基因集中占的比例要显著高于在所有背景基因集中所占的比例。比如上面的例子，深圳市大学生显著富集，意思就是深圳市本科毕业的人口所占深圳市总人口的比例显著高于广东省本科毕业人口在广东省总人口中所占的比例。