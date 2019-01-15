# 日文相關

---
## python漢字判定  [Link](https://minus9d.hatenablog.com/entry/2015/07/16/231608)

```
def is_japanese(string):
    for ch in string:
        name = unicodedata.name(ch) 
        if "CJK UNIFIED" in name \
        or "HIRAGANA" in name \
        or "KATAKANA" in name:
            return True
    return False

>>> import unicodedata
>>> unicodedata.name('你')
'CJK UNIFIED IDEOGRAPH-4F60'
>>> unicodedata.name('桜')
'CJK UNIFIED IDEOGRAPH-685C'
>>> unicodedata.name('あ')
'HIRAGANA LETTER A'
>>> unicodedata.name('ア')
'KATAKANA LETTER A'
>>> unicodedata.name('a')
'LATIN SMALL LETTER A'    

```

---

