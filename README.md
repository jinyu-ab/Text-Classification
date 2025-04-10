# Text-Classification

# 0.项目介绍
``文本分类（Text Classification）``是自然语言处理中的一个重要应用技术，根据文档的内容或主题，自动识别文档所属的预先定义的类别标签。

本项目基于scikit-learn机器学习Python库，使用分词算法+分类模型对中文文本进行分类。其中，分词基于jieba分词算法，特征提取基于TF-IDF算法，分类算法分别使用了朴素贝叶斯、KNN和GBDT算法，通过输出宏平均、微平均在准确度、召回率及F1值三个指标上的表现，以及混淆矩阵，对三种模型在该数据集上的分类效果进行评估，实现了一个比较完整的中文文本分类程序。

# 1.数据集
项目选用了了开源的中文文本分类数据集THUCNews，介绍如下：
 * THUCNews 是根据新浪新闻 RSS 订阅频道 2005~2011 年间的历史数据筛选过滤生成，包含 74 万篇新闻文档（2.19 GB），均为 UTF-8 纯文本格式。
* 由于原数据集较大，项目在原始新浪新闻基础上提取部分数据再使用：从原始数据集中选取六个模块（"体育", "财经", "房产", "家居", "教育", "科技"）各5000篇，共30000 篇；每篇新闻样本由类别标签（lable）和内容（text）组成；将新数据集按照 8:1:1 划分成训练集（train set）、验证集（validate set）、测试集（test set）。

# 2.项目思路
* 环境准备：使用pip安装并导入相关库，包括pandas、jieba、
sklearn-learn、matplotlib、numpy等
* 数据加载：使用pandas库加载数据集
* 中文预处理：使用jieba分词算法对原始数据进行分词，去除文本中的停用词
* 数据集划分：将数据集划分为训练集、验证集和测试集（训练集:验证集:测试集=8:1:1） 
* 特征提取：使用TF-IDF算法对分词后的文本进行特征提取，并输出向量化后特征矩阵的维度
* 分类模型训练：使用三种分类算法（朴素贝叶斯、KNN和GBDT）对特征矩阵进行训练，构建分类模型
* 模型评估与可视化：对三种分类算法的模型进行评估，输出准确度、召回率及F1值三个指标上的表现，以及混淆矩阵

# 3.目录结构描述
* ReadMe.md:本项目的帮助文档，包含项目介绍、数据集介绍、项目思路、文件结构、环境依赖等。
* stopwords.txt:本项目使用的停用词表，包含一些常见的停用词。
* text_classification.ipynb:本项目的完整代码文件，使用Jupyter Notebook打开，包含数据预处理、特征提取、模型训练和模型评估等步骤。 

# 4.环境依赖
* Python 3.11.9
* pandas
* numpy
* jieba 
* sklearn-learn
* matplotlib 
* seaborn

# 5.结论
**GBDT**是当前任务的最佳选择，综合性能显著优于其他模型。若需快速部署，**朴素贝叶斯**是可靠的备选方案，而**KNN**需进一步优化，考虑可能的改进方向。


