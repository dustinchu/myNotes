# 基於遞歸神經網絡的日語標記器

[github Link](https://github.com/taishi-i/nagisa)

---

[！[建立狀態]（https://travis-ci.org/taishi-i/nagisa.svg?branch=master）]（https://travis-ci.org/taishi-i/nagisa）
[！[文檔狀態]（https://readthedocs.org/projects/nagisa/badge/?version=latest）]（https://nagisa.readthedocs.io/en/latest/?badge=latest）
[！[PyPI中（https://img.shields.io/pypi/v/nagisa.svg）（https://pypi.python.org/pypi/nagisa）

Nagisa是日語分詞/ POS標記的python模塊。
它旨在成為一個簡單易用的工具。

此工具具有以下功能。
- 基於遞歸神經網絡。
- 分詞模型使用字符和單詞級特徵[[池田+]]（http://www.anlp.jp/proceedings/annual_meeting/2017/pdf_dir/B6-2.pdf）。
-  POS標記模型使用標記字典信息[[Inoue +]]（http://www.aclweb.org/anthology/K17-1042）。

有關更多詳細信息，請參閱以下鏈接。
- 日語文章[這裡]（https://qiita.com/taishi-i/items/5b9275a606b392f7f58e）。
- 文檔[這裡]（https://nagisa.readthedocs.io/en/latest/?badge=latest）。

安裝
=============

需要Python 2.7.x或3.5+。
該工具使用[DyNet]（https://github.com/clab/dynet）（動態神經網絡工具包）來計算神經網絡。
您可以使用以下命令安裝nagisa。
```慶典
pip安裝nagisa
```
如果你在Windows上使用nagisa，請使用python 3.5+運行它。

基本用法
======
日語的分詞和POS標記示例。

```蟒蛇
進口nagisa

text ='Pythonで簡単に使えるツールです'
words = nagisa.tagging（text）
打印（字）
＃=> Python /名詞で/助詞簡単/形狀詞に/助動詞使える/動詞ツール/名詞です/助動詞

＃獲取單詞列表
打印（words.words）
＃=> ['Python'，'で'，'簡単'，'に'，'使える'，'ツール'，'です']

＃獲取POS標籤列表
打印（words.postags）
＃=> ['名詞'，'助詞'，'形狀詞'，'助動詞'，'動詞'，'名詞'，'助動詞']
```

後處理功能
=====
通過特定POS標籤過濾和轉發單詞。
```蟒蛇
＃過濾特定POS標籤的字樣。
words = nagisa.filter（text，filter_postags = ['助詞'，'助動詞']）
打印（字）
＃=> Python /名詞簡単/形狀詞使える/動詞ツール/名詞

#Extarct只有名詞。
words = nagisa.extract（text，extract_postags = ['名詞']）
打印（字）
＃=> Python /名詞ツール/名詞

＃這是nagisa中可用的POS標籤列表。
打印（nagisa.tagger.postags）
＃=> ['補助記號'，'名詞'，...，'URL']
```

以簡單的方式添加用戶詞典。
```蟒蛇
＃如果single_word_list中包含一個單詞，則將其識別為單個單詞。
text =“ニューラルネットワークを使ってます。”
tagger_nn = nagisa.Tagger（single_word_list = ['ニューラルネットワーク']）
打印（tagger_nn.tagging（文本））
＃=>ニューラルネットワーク/名詞を/助詞使っ/動詞て/助動詞ます/助動詞./補助記號
```


訓練模型
======
Nagisa（v0.2.0 +）提供了一種簡單的訓練方法
用於聯合分詞和序列標記（例如，POS標記，NER）模型。


train / dev / test文件的格式是tsv。
每行是`word`和`tag`，一行由`word` \ t（tab）`tag`表示。
請注意，您將EOS放在句子之間。


```
$ cat sample.train
唯一NOUN
のADP
趣味NOU
はADP
料理NOUN
EOS
とてもADV
おいしかっADJ
たAUX
ですAUX
PUNCT
EOS
ドルNOUN
はADP
主要ADJ
通貨NOUN
EOS
```

```蟒蛇
＃完成訓練後，保存三個模型文件（* .vocabs，* .params，* .hp）。
nagisa.fit（train_file =“sample.train”，dev_file =“sample.dev”，test_file =“sample.test”，model_name =“sample”）

＃通過加載訓練的模型文件來構建標記器。
sample_tagger = nagisa.Tagger（vocabs ='sample.vocabs'，params ='sample.params'，hp ='sample.hp'）

text =“福岡·博多の観光情報”
words = sample_tagger.tagging（text）
打印（字）
＃>福岡/ PROPN·/ SYM博多/ PROPNの/ ADP観光/ NOUN情報/ NOUN
```
