# 情感分析概述

该项目主是对自然语言处理领域中的情感分析技术的一个总结整理与概述。主要包括以下
内容

## 方法概述
根据分析载体的不同，情感分析会涉及很多主题，包括针对电影评论，商品评价，新闻和博客等的情感分析。在情感分析领域，文本识别可以划分为积极和消极两类，或者积极，消极和中性等，分析的主要方法有：
 ###字典分析
        字典分析运用了有标记词汇组成的字典，使用词法分析器将输入文本转化为单词序列，将每一个新的单词
	与字典中的词汇进行匹配。如果有一个积极的匹配，分数加到输入文本的总分中。
        例如：
        如果戏剧性在字典中是一个积极的匹配，那么文本总分会递增，若相反，会将总分进行减少。
        文本的分类取决于文本的总得分。
###基于机器学习的分析
        机器学习的方式具有较高的适用性和准确性。在情感分析中主要使用的方式是监督学习方法。可以分为三个步骤：数据收集，预处理，训练分类。在训练过程中，需要提供一个标记语料库作为训练数据。分类器
	使用乙烯类特征向量对目标数据进行分类。在机器学习技术中，决定分类器准确率的关键是合适的特征选
	择。通常来说，使用Ngram模型，tf-idf，word2vec等。算法模型可以使用传统的机器学习方法，比如逻
        辑回归，决策树，SVM，贝叶斯等，也可以是CNN、LSTM等深度学习算法。
        机器学习技术面临很多挑战：分类器的设计，训练数据的获取，对未知短语的识别等，相比词典分析方式
        在字典大小呈指数增长的时候依然可以很好的工作。
###混合分析方式
## 文献综述
###1、2017年的survey  
    论文主要是阐述在情感分析方面的基本方法的survey。
    Published in: 2017 International Conference on I-SMAC (IoT in Social, Mobile, Analytics and Cloud) (I-SMAC)
    文档位置：document目录。
    论文主要内容：
        特征提取方式：论文是关于英文的情感分析，提取方式可以参考。
	分类方法：词典和机器学习方式。
                机器学习方式：传统机器学习和神经网络方式。
###2、论文：Apply Word Vectors for Sentiment Analysis of APP Reviews 
   The 2016 3rd International Conference on Systems and Informatics (ICSAI 2016)
   	
## 工具总结

### 开源工具包
####python机器学习库：
    scikit-learn：机器学习库。
####nlp处理工具：
    NLTK:用户python 自然语言处理库。
    Ansj是由孙健（ansjsun）开源的一个中文分词器，为ICTLAS的Java版本，也采用了Bigram + HMM分词模型
    Jieba是由fxsjy大神开源的一款中文分词工具，一款属于工业界的分词工具——模型易用简单、代码清晰可读，推荐有志学习NLP或Python的读一下源码。与采用分词模型Bigram + HMM 的ICTCLAS 相类似，Jieba采用的是Unigram + HMM。Unigram假设每个词相互独立，则分词组合的联合概率：
    LTP是哈工大开源的一套中文语言处理系统，涵盖了基本功能：分词、词性标注、命名实体识别、依存句法分析、语义角色标注、语义依存分析等。   
    CoreNLP是由斯坦福大学开源的一套Java NLP工具，提供诸如：词性标注（part-of-speech (POS) tagger）、命名实体识别（named entity recognizer (NER)）、情感分析（sentiment analysis）等功能。
    gensim：开源的第三方python工具包，用于从原始的非结构化文本中，无监督的学习到文本隐层的主题向量表达。支持TF-IDF、LSA、LDA和word2vec在内的多种主题模型算法，支持流式训练，并提供了诸如相似度计算，信息检索等一系列常用任务的api接口。
###  API 接口