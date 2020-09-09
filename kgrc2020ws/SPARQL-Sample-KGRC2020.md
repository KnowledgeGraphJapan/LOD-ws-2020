# ナレッジグラフ推論チャレンジ2020用SPARQLクエリのサンプル
[人工知能学会SWO研究会ワークショップ「ナレッジグラフ推論チャレンジ2020技術勉強会」](https://kgrc2020ws.peatix.com/)で紹介した，
SPARQLクエリのサンプルです．  

提供されているナレッジグラフの入手先は[こちら](https://challenge.knowledge-graph.jp/2020/rdf.html)，
サンプルクエリの説明を含む資料は[こちら](https://github.com/KnowledgeGraphJapan/LOD-ws-2020/blob/master/kgrc2020ws/KGRC-WS-ChallengIntro-KG-Schema_2020-0909.pdf)をご覧ください．  
  
サンプルクエリを実行するには，
- SPARQLエンドポイント  
http://knowledge-graph.jp/sparql.html  
  
にクエリをコピー＆貼り付けして，実行してください．


## ｢まらだのひも」の場面36の全トリプル（述語・目的語）を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  <http://kgc.knowledge-graph.jp/data/SpeckledBand/36> ?p ?o .
}
```


## ｢まらだのひも」の場面36のhasPredicate（その場面の内容を表す述語）を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  <http://kgc.knowledge-graph.jp/data/SpeckledBand/36> kgc:hasPredicate ?o .
}
```

## ｢まらだのひも」の場面36のsubject（その場面の主語）を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  <http://kgc.knowledge-graph.jp/data/SpeckledBand/36> kgc:subject ?o .
}
```
## ｢まらだのひも」で用いられているhasPredicate（その場面の内容を表す述語）の一覧を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT ?o
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  ?s kgc:hasPredicate ?o .
}
```
## ｢まらだのひも」のSituation（事実・状況の描写）の一覧を取得する
```
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  ?s rdf:type kgc:Situation .
}
```
## ｢まらだのひも」の全場面の一覧を取得する
```
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  ?s rdf:type/rdfs:subClassOf kgc:Scene .
  ?s rdf:type ?o .
}
```
## ｢全小説」で述語がmeetの場面の一覧を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>
SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
FROM <http://kgc.knowledge-graph.jp/data/DancingMen>
FROM <http://kgc.knowledge-graph.jp/data/ACaseOfIdentity>
FROM <http://kgc.knowledge-graph.jp/data/DevilsFoot>
FROM <http://kgc.knowledge-graph.jp/data/CrookedMan>
WHERE {
  ?s kgc:hasPredicate <http://kgc.knowledge-graph.jp/data/predicate/meet> .
}
```
## ｢まらだのひも」で用いられているhasProperty（その場面の内容を表す状態）の一覧を取得する
```
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT ?o
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  ?s kgc:hasProperty ?o .
}
```
## ｢まらだのひも」で場面間のつながりの一覧を取得する
```
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX kgc: <http://kgc.knowledge-graph.jp/ontology/kgc.owl#>

SELECT DISTINCT *
FROM <http://kgc.knowledge-graph.jp/data/SpeckledBand>
WHERE {
  ?s rdf:type/rdfs:subClassOf kgc:Scene .
  ?o rdf:type/rdfs:subClassOf kgc:Scene .
  ?s ?p ?o .
}
```
