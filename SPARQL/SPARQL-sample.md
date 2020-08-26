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

## 例1-1+）「大阪電気通信大学(Q7105556)」（主語）の「位置する行政区(P131)」（述語）となる目的語（?o）を取得する【＋名称（ラベル）も合わせて取得する】　
```
select ?o ?label
where{
    <http://www.wikidata.org/entity/Q7105556>  <http://www.wikidata.org/prop/direct/P131> ?o .
    ?o <http://www.w3.org/2000/01/rdf-schema#label> ?label . #名称の取得
    FILTER(lang(?label)="ja")     # 名称の言語を日本語(ja)に限定
}
```
[クエリを実行](https://w.wiki/aMz)


# 検索例２：<主語>-<述語>を指定して<目的語>を取得する
## 例2-1）「位置する行政区（P131）」（述語）が「寝屋川市（Q389633）」（目的語）となる「主語（?s）」の一覧を取得する　　
```
select ?s
where{
    ?s  <http://www.wikidata.org/prop/direct/P131> <http://www.wikidata.org/entity/Q389633> .
}
LIMIT 100
```
[クエリを実行](https://w.wiki/aMv)

