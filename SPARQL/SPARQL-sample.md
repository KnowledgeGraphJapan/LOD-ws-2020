# 検索例１：<主語>-<述語>を指定して<目的語>を取得する
## 例1-1）「大阪電気通信大学(Q7105556)」（主語）の「位置する行政区(P131)」（述語）となる目的語（?o）を取得する　
```
select ?o
where{
    <http://www.wikidata.org/entity/Q7105556>  <http://www.wikidata.org/prop/direct/P131> ?o .
}
```
[クエリを実行](https://w.wiki/aMq)

## 例1-2）「大阪電気通信大学(Q7105556)」（主語）の「設立(P571)」（述語）となる目的語（?o）を取得する　
```
select ?o
where{
    <http://www.wikidata.org/entity/Q7105556>  <http://www.wikidata.org/prop/direct/P571> ?o .
}
```
[クエリを実行](https://w.wiki/aMs)

