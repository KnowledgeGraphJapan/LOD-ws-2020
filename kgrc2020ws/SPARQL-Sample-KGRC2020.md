# ナレッジグラフ推論チャレンジ2020用SPARQLクエリのサンプル
[人工知能学会SWO研究会ワークショップ「ナレッジグラフ推論チャレンジ2020技術勉強会」](https://kgrc2020ws.peatix.com/)で紹介した，
SPARQLクエリのサンプルです．  

提供されているナレッジグラフの入手先は[こちら](https://challenge.knowledge-graph.jp/2020/rdf.html)，
サンプルクエリの説明を含む資料は[こちら](https://github.com/KnowledgeGraphJapan/LOD-ws-2020/blob/master/kgrc2020ws/KGRC-WS-ChallengIntro-KG-Schema_2020-0909.pdf)をご覧ください．


## ｢まらだのひも」の場面36の全トリプル（述語・目的語）を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  <http://kgc.knowledge-graph.jp/data/SpeckledBand/36> ?p ?o .
}
```
[クエリの実行](http://knowledge-graph.jp/sparql.html#query=PREFIX%20kgc%3A%20%3Chttp%3A%2F%2Fkgc.knowledge-graph.jp%2Fontology%2Fkgc.owl%23%3E%0A%0ASELECT%20DISTINCT%20*%0AFROM%20%3Chttp%3A%2F%2Fkgc.knowledge-graph.jp%2Fdata%2FSpeckledBand%3E%0AWHERE%20%7B%0A%20%20%3Chttp%3A%2F%2Fkgc.knowledge-graph.jp%2Fdata%2FSpeckledBand%2F36%3E%20%3Fp%20%3Fo%20.%0A%7D&endpoint=http%3A%2F%2Fkg.hozo.jp%2Ffuseki%2Fkgrc%2Fsparql&requestMethod=POST&tabTitle=Query%201&headers=%7B%7D&contentTypeConstruct=text%2Fturtle%2C*%2F*%3Bq%3D0.9&contentTypeSelect=application%2Fsparql-results%2Bjson%2C*%2F*%3Bq%3D0.9&outputFormat=table)

## 
