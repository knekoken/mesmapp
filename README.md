# mesmapp powered by CesiumJS
地震に関するオープンデータをWebGISで3次元的に可視化して，防災に対する理解を深めるWebサービス

[URL](https://www.mesmapp.com)


サービス名は，下記から由来しています。
- **M**achine Learning **E**nhanced **S**tructural **M**onitoring
- **Me**ga **S**cale **M**onitoring
- **M**ulti-scale **E**nhanced **S**tructural **M**onitoring
- **Me**tropolitan **S**cale **M**onitoring

<h2 style="color:rgba(255, 255, 255, 0.411)">Webサービスのイメージ</h2>

![MeSM Logo](https://private-user-images.githubusercontent.com/199451470/413601653-a4325c7b-1c9c-45fd-86c8-d309f4aeddf5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3Mzk2OTY0MDMsIm5iZiI6MTczOTY5NjEwMywicGF0aCI6Ii8xOTk0NTE0NzAvNDEzNjAxNjUzLWE0MzI1YzdiLTFjOWMtNDVmZC04NmM4LWQzMDlmNGFlZGRmNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMjE2JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDIxNlQwODU1MDNaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mYTZlMTI1MGQ0ZDg4MmFiZjcyMjYwZDE4NzExOTg2ODMzM2MzM2M5NjVmMjRiNGI0ZTcyNmQ5ZDVkNTk3YzQ2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.teiK4Bs586HIhr55VRjQjsyyAnM_qo_AFYrWHrxtWW0)

<h2 style="color:rgba(255, 255, 255, 0.411)">データの出典</h2>
<ul>
    <li>このWebアプリは，<a href="https://cesium.com" target="_blank" style="color:orange; text-decoration: none;">CesiumJS</a>のJavascriptライブラリを用いて開発されています。</li>
    <li>画像レイヤーの一部には，<a href="https://docs.mapbox.com/api/maps/static-tiles/" target="_blank" style="color:orange; text-decoration: none;">MapboxのStatic Tiles API</a>を使用しています。月間タイルリクエスト数が限られているため，予告なく機能を停止する場合があります。</li>
    <li>建物の3D tilesは，国土交通省が開発し，<a href="https://front.geospatial.jp" target="_blank" style="color:orange; text-decoration: none;">G空間情報センター</a>が配布しているProject PLATEAUのデータを利用しています。</li>
    <li>最近の地震情報は，<a href="https://www.data.jma.go.jp/svd/eqdb/data/shindo/index.html" target="_blank" style="color:orange; text-decoration: none;">気象庁 震度データベース検索</a>を利用しています。</li>
    <li>日本付近で発生した主な被害地震の情報には，<a href="https://www.data.jma.go.jp/eqev/data/higai/higai1996-new.html" target="_blank" style="color:orange; text-decoration: none;">気象庁のHP</a>を引用しています。</li>
    <li>震源付近での過去の被害地震には，<a href="https://official.rikanenpyo.jp/" target="_blank" style="color:orange; text-decoration: none;">理科年表の日本付近のおもな被害地震年代表</a>を利用してます。</li>
    <li>ゆれの状況の説明には，<a href="https://www.jma.go.jp/jma/kishou/know/shindo/kaisetsu.html" target="_blank" style="color:orange; text-decoration: none;">気象庁震度階級関連解説表</a>を引用しています。</li>
    <li>震源データについては，<a href="https://www.kyoshin.bosai.go.jp/kyoshin/" target="_blank" style="color:orange; text-decoration: none;">防災科学技術研究所の強震観測網 (K-NET, KiK-net) </a>を利用しています。</li>
<!--    <li>緊急地震速報のデータは，<a href="http://www.ceorka.org" target="_blank" style="color:orange; text-decoration: none;">関西地震観測研究協議会 (CEORKA) </a>のサービスを利用しています。</li>-->
    <li>建物観測点として，<a href="https://smo.kenken.go.jp/ja" target="_blank" style="color:orange; text-decoration: none;">建築研究所の強震観測網 BRI Strong Motion Network</a>を引用しています。</li>
    <li>首都圏地震観測網には，<a href="https://www.mesonet.bosai.go.jp/mrportal/top"  target="_blank" style="color:orange; text-decoration: none;">MeSO-net</a>を利用してます。</li>
    <li>主要活断層データは，<a href="https://www.j-shis.bosai.go.jp" target="_blank" style="color:orange; text-decoration: none;">地震ハザードステーション (J-SHIS) </a>を利用しています。</li>
    <li>確率論的地震動予測地図は，<a href="https://www.j-shis.bosai.go.jp/api-sstruct-meshinfo" target="_blank" style="color:orange; text-decoration: none;">地震ハザードステーション (J-SHIS) の公開データ</a>を利用しています。</li>
    <li>表層地盤情報や地盤増幅率は，<a href="https://www.j-shis.bosai.go.jp/api-sstruct-meshinfo" target="_blank" style="color:orange; text-decoration: none;">地震ハザードステーション (J-SHIS) の公開データ</a>を利用しています。</li>
    <li>プレート境界として，<a href="https://www.usgs.gov/programs/earthquake-hazards/google-earthtmkml-files"  target="_blank" style="color:orange; text-decoration: none;">USGSのGoogle Earth/KML Files (Tectonic Plate Boundaries) </a>を引用しています。</li>
    <li>日本の活火山分布として，<a href="https://www.data.jma.go.jp/svd/vois/data/tokyo/STOCK/bulletin/catalog/appendix/v_active.html"  target="_blank" style="color:orange; text-decoration: none;">気象庁の日本の活火山分布図</a>を引用しています。</li>
    <li>リバースジオコーディングには，<a href="https://developer.yahoo.co.jp/sitemap/" target="_blank" style="color:orange; text-decoration: none;">Web Services by Yahoo! JAPAN</a>を使用しています。</li>
    <li>津波・洪水範囲の想定は，<a href="https://disaportal.gsi.go.jp/index.html" target="_blank" style="color:orange; text-decoration: none;">ハザードマップポータルサイトのオープンデータ</a>を利用しています。</li>
    <li>指定緊急避難場所の表示には，<a href="https://www.gsi.go.jp/bousaichiri/hinanbasho.html" target="_blank" style="color:orange; text-decoration: none;">国土地理院のデータ</a>を用いています。</li>
    <li>避難場所（東京都）の表示には，<a href="https://catalog.data.metro.tokyo.lg.jp/dataset/t000003d0000000093" target="_blank" style="color:orange; text-decoration: none;">東京オープンデータカタログ</a>を用いています。</li>
    <li>自然災害伝承碑の表示には，<a href="https://www.gsi.go.jp/bousaichiri/denshouhi_datainfo.html" target="_blank" style="color:orange; text-decoration: none;">国土地理院のデータ</a>を用いています。</li>
    <li>緊急輸送道路の表示には，<a href="https://nlftp.mlit.go.jp/ksj/gml/datalist/KsjTmplt-N10-v1_1.html" target="_blank" style="color:orange; text-decoration: none;">国土数値情報ダウンロードサイトのデータ</a>を用いています。</li>
    <li>世界の地震の表示には，<a href="https://earthquake.usgs.gov/data/comcat/" target="_blank" style="color:orange; text-decoration: none;">USGSが配信しているデータ</a>を用いています。</li>
    <li>地形データは，<a href="https://github.com/Project-PLATEAU/plateau-streaming-tutorial/blob/main/terrain/plateau-terrain-streaming.md" target="_blank" style="color:orange; text-decoration: none;">測量法に基づく国土地理院長承認（使用）R3JHs 778</a>を得て使用しました。</li>
    <!--   <li>指定緊急避難場所の画像は，<a href="https://www.town.ino.kochi.jp/bousai/shoubou_hinan/1727/" target="_blank" style="color:orange; text-decoration: none;">いの町のWebサイト</a>で提供されているファイルを利用しています。</li> -->
</ul>







