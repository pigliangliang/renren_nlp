#机器学习特征提取
##文字特征提取
###词库表示
词袋模型  
    
    词袋模型忽略词序，语法，仅仅是作为一个词的集合，称为词典。词典的元素数据量构成词向量的维度大小。
    在构造特征向量的时候，用词典来表示词汇表与特征向量的索引关系。
    两种方式  
      词频做向量值
      词权重做向量值（TFIDF/CHI/MI）
    
词向量  
    
    word2vec是谷歌提出基于上下文语境来获取的词向量。
    一般使用gensim开源库实现。
    或者使用深度学习平台，比如TensorFlow或者caffe训练词向量。
    训练过程：
    在TensorFlow 平台上
    首先加载语料，分词。构建词典。获取频率靠前的比如50000单词。
    其次，构建单词：索引的形式保存，对分词文本进行索引形式的转化，未出现在词典中的单词索引为0。这样整个分词文本转化索引形式的的向量。维度大小为最大词典长度。
    最后batch数据：lable 定义为数据的后移n位的batch长度。
    构建网络模型，训练优化参数。
    
    
    
总结

    机器学习方式
    输入算法模型的是人工提取完成的特征向量，而不是原始文本的向量，比如，
    文本：手机性能不错，价格不贵，性价比很高。
    提取特征：性能不错，不贵，性价比，很高。使用tf-idf,ngram，pmi，词频等方式处理，提取在特征。
    特征向量转化：原始文本转化为特征向量。
    算法模型：选择机器学习算法
    训练，测试等。
    深度学习方式
    结合词向量，可以使提前生成好的的词向量，加载到模型中，或者是在模型训练的过程中在嵌入层添加训练词向量的过程。将原始文本直转化为向量方式，有深度学习模型本身去提取文本特征，不断修正模型参数，最终完成模型训练。
    首先向量训练：开源库方式
                google word2vec 是c版本
                Python gensim 库
                自己训练，需要大量的语料库，否则生成的词向量无法覆盖全部的单词。
    训练平台：比如TensorFlow 提供接口查询文本中每个词的向量完成模型输入。
    优化模型参数，保存模型。
    
#基于深度学习的NLP算法
深度学习作为机器学习的重要分支，可以自动地学习合适的特征与多层次的表达输出，在nlp领域，主要在信息抽取，命名实体实体识别，词性标注，文本分析，拼写表达，语音识别，机器翻译，金融领域的情感分析等方向有成功的应用。
和传统的机器学习方式相比，深度学习的重要特性是，用词向量来表示各种级别的元素。传统的算法一般会用统计等方法去标注，深度学习会直接通过词向量表示，然后通过深度网络进行自动学习。


##多层感知机
包含输入，输出，隐层。
输入层接收输入信息，不进行函数处理，只赋予不同输入的不同权重
隐层和输出层进行更高层次的抽象决策。
##神经网络模型

将多个单一的神经单元组合到一起，这样一个神经元的输出就可以是另一个神经元的输入。
###前向传播
从输入到输出的逐层计算传递过程。
###反向传播
链式法则和梯度求导
###梯度下降

