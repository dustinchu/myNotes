# 其他

## deeplearnang 4j  日本人 介紹 http://qiita.com/wmeddie/items/8f036e3eadfa3e012eed

---

##日本 dl4j  音頻 論文 訓練了解音樂  使用 pudub將音樂分割 內文裡有 pudub github [Link](http://qiita.com/himono/items/a94969e35fa8d71f876c)

---

## 我們來看看ND4J可以進行什麼計算的簡單例子。我們用ND4J使用的類型INDArray是擴展類型Array。我們從導入以下依賴關係開始：[link](http://nd4j.org/documentation.html)

---

## ND4J  INDArray  用法

- 由於有很多情況 單獨使用ND4J可以方便地使用，我們在研究DL4J的解釋之前，先簡要介紹一下如何使用ND4J。如果您想單獨使用- - ND4J，一旦創建了一個新的Maven項目，那麼可以使用ND4J添加以下代碼pom.xml：

* 複製

```
<properties>
   <nd4j.version>0.4-rc3.6</nd4j.version>
</properties>

<dependencies>
   <dependency>
       <groupId>org.nd4j</groupId>
       <artifactId>nd4j-jblas</artifactId>
       <version>${nd4j.version}</version>
   </dependency>
   <dependency>
       <groupId>org.nd4j</groupId>
       <artifactId>nd4j-perf</artifactId>
       <version>${nd4j.version}</version>
   </dependency>
</dependencies>
```

- 在這裡，<nd4j.version>介紹ND4J的最新版本，但是當您實際執行代碼時，請檢查是否更新。此外，在使用時，從CPU切換到GPU很容易ND4J。如果您使用版本7.0安裝CUDA，那麼您所做的只是定義artifactId如下：

複製
```
<dependency>
   <groupId>org.nd4j</groupId>
   <artifactId>nd4j-jcublas-7.0</artifactId>
   <version>${nd4j.version}</version>
</dependency>
```
您可以<artifactId>根據您的配置替換版本。


## DL4J：ETL用户指南 中文官網 https://deeplearning4j.org/cn/etl-userguide

---

## 日本dl4j word2vec http://blog.apitore.com/2016/09/19/deeplearning4j-jwikipedia-word2vec/