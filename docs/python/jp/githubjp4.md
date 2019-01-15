# 用純Python編寫的日本形態分析引擎 

https://github.com/mocobeta/janome  (github Link)

=======
Janome
=======



Janome is a Japanese morphological analysis engine written in pure Python.

General documentation:

https://mocobeta.github.io/janome/en/ (English)

https://mocobeta.github.io/janome/ (Japanese)

Requirements
=============

Python 2.7.x or 3.3+ is required.

Install
========

[Note] This consumes about 500 MB memory for building.



  ```(venv) $ python setup.py install```

Run
====



```  
(env) $ python
from janome.tokenizer import Tokenizer
t = Tokenizer()
for token in t.tokenize(u'すもももももももものうち'):
 print(token)
 ```

  ```
  すもも 名詞,一般,*,*,*,*,すもも,スモモ,スモモ
  も    助詞,係助詞,*,*,*,*,も,モ,モ
  もも  名詞,一般,*,*,*,*,もも,モモ,モモ
  も    助詞,係助詞,*,*,*,*,も,モ,モ
  もも  名詞,一般,*,*,*,*,もも,モモ,モモ
  の    助詞,連体化,*,*,*,*,の,ノ,ノ
  うち  名詞,非自立,副詞可能,*,*,*,うち,ウチ,ウチ
```

```

  (env) $ python
  >>> from janome.tokenizer import Tokenizer
  >>> from janome.analyzer import Analyzer
  >>> from janome.charfilter import *
  >>> from janome.tokenfilter import *
  >>> text = u'蛇の目はPure Ｐｙｔｈｏｎな形態素解析器です。'
  >>> char_filters = [UnicodeNormalizeCharFilter(), RegexReplaceCharFilter(u'蛇の目', u'janome')]
  >>> tokenizer = Tokenizer()
  >>> token_filters = [CompoundNounFilter(), POSStopFilter(['記号','助詞']), LowerCaseFilter()]
  >>> a = Analyzer(char_filters, tokenizer, token_filters)
  >>> for token in a.analyze(text):
    print(token)
  ```
```  
  janome  名詞,固有名詞,組織,*,*,*,*,*,*
  pure    名詞,固有名詞,組織,*,*,*,*,*,*
  python  名詞,一般,*,*,*,*,*,*,*
  な       助動詞,*,*,*,特殊・ダ,体言接続,だ,ナ,ナ
  形態素解析器  名詞,複合,*,*,*,*,形態素解析器,ケイタイソカイセキキ,ケイタイソカイセキキ
  です     助動詞,*,*,*,特殊・デス,基本形,です,デス,デス
```

License
========

Licensed under Apache License 2.0 and uses the MeCab-IPADIC dictionary/statistical model.

See LICENSE.txt and NOTICE.txt for license details.

Acknowledgement
================

Special thanks to @ikawaha, @takuyaa and @nakagami.

Copyright
==========

Copyright(C) 2015, Tomoko Uchida. All rights reserved.