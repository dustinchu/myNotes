# CJK（中文，日文和韓文）語言數據的Python庫 (https://cihai.git-pull.com)


[github Link](https://github.com/cihai/cihai)

API / Library (this repository)
"""""""""""""""""""""""""""""""

```
 $ pip install --user cihai
``` 

```
   from cihai.core import Cihai

   c = Cihai()

   if not c.unihan.is_bootstrapped:  # download and install Unihan to db
       c.unihan.bootstrap(unihan_options)

   query = c.unihan.lookup_char('好')
   glyph = query.first()
   print("lookup for 好: %s" % glyph.kDefinition)
   # lookup for 好: good, excellent, fine; well

   query = c.unihan.reverse_char('good')
   print('matches for "good": %s ' % ', '.join([glph.char for glph in query]))
   # matches for "good": 㑘, 㑤, 㓛, 㘬, 㙉, 㚃, 㚒, 㚥, 㛦, 㜴, 㜺, 㝖, 㤛, 㦝, ...
```

See `API`_ documentation and `/examples
(https://github.com/cihai/cihai/tree/master/examples)


CLI (`cihai-cli`_)
""""""""""""""""""

```

   # stable
   $ pip install --user cihai-cli

   # pre-release
   $ pip install --user --pre cihai[cli]

```
```
   # character lookup
   $ cihai info 好
   char: 好
   kCantonese: hou2 hou3
   kDefinition: good, excellent, fine; well
   kHangul: 호
   kJapaneseOn: KOU
   kKorean: HO
   kMandarin: hǎo
   kTang: '*xɑ̀u *xɑ̌u'
   kTotalStrokes: '6'
   kVietnamese: háo
   ucn: U+597D

   # reverse lookup
   $ cihai reverse library
   char: 圕
   kCangjie: WLGA
   kCantonese: syu1
   kCihaiT: '308.302'
   kDefinition: library
   kMandarin: tú
   kTotalStrokes: '13'
   ucn: U+5715
```
   --------

UNIHAN data
"""""""""""

All datasets that cihai uses have stand-alone tools to export their data.
No library required.

- `unihan-etl <https://unihan-etl.git-pull.com>`_ - `UNIHAN`_ data
  exports for csv, yaml and json.

