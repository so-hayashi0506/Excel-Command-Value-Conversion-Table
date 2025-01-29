
## 概要

本書ではV2X-GWのEV充放電制御機能におけるGWからPCSへの指令値出力仕様を定義する。
対象とする機能は下記の通り。

・スケジュール充放電
・ECHONET Lite充放電

■関連資料
・(環)DES-G181016306_次世代GW端末_設定・データ仕様書
・(環)DES-M180920048-2_次世代GW端末ECHONET Lite機能仕様書(別紙)プロパティ詳細



***

ここだと旨いこと連絡することが可能になる。


Input欄記載の充放電を実行したい場合は、PCSにOutPut記載の変数（値）を書き込み、動作指令を発行する。

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 8%" />
</colgroup>
<thead>
<tr>
<th rowspan="2" style="text-align: center;"><strong>Input<br />
（GWからの充放電設定値）</strong></th>
<th colspan="12" style="text-align: center;">　</th>
<th style="text-align: center;"><strong>　</strong></th>
</tr>
<tr>
<th colspan="13" style="text-align: center;">　</th>
</tr>
</thead>
<tbody>
<tr>
<th style="text-align: center;">充放電モード<br />
指令値(※1)</th>
<td style="text-align: center;">EV充放電制御<br />
モード</td>
<td style="text-align: center;">EV充電目標値<br />
（外部制御）</td>
<td style="text-align: center;">EV放電目標値<br />
（外部制御）</td>
<td style="text-align: center;">EV安心充電指定</td>
<td style="text-align: center;">EV（KPEP)<br />
充放電方式</td>
<td style="text-align: center;">EV（KPEP)<br />
充放電電力指定</td>
<td style="text-align: center;">EV（KPEP)<br />
充放電電力設定</td>
<td style="text-align: center;">EV（KPEP)<br />
系統電力指定</td>
<td style="text-align: center;">EV（KPEP)<br />
系統電力設定</td>
<td style="text-align: center;">EV（KPEP)<br />
充放電<br />
電力量指定</td>
<td style="text-align: center;">EV（KPEP)<br />
充放電<br />
電力量設定</td>
<td style="text-align: center;">EV放電停止SOC<br />
(安心モード)</td>
<td style="text-align: center;">電力融通モード指定<br />
&lt;A5&gt;</td>
</tr>
<tr>
<th style="text-align: left;"><strong>GWからの書き込み変数</strong></th>
<td style="text-align: center;">41:2052</td>
<td style="text-align: center;">41:2057</td>
<td style="text-align: center;">41:2058</td>
<td style="text-align: center;">41:2059</td>
<td style="text-align: center;">41:205A</td>
<td style="text-align: center;">41:205B</td>
<td style="text-align: center;">C1:110A</td>
<td style="text-align: center;">41:205C</td>
<td style="text-align: center;">C1:110B</td>
<td style="text-align: center;">41:205D</td>
<td style="text-align: center;">C1:110C</td>
<td style="text-align: center;">81:2016</td>
<td style="text-align: center;">41:2067</td>
</tr>
<tr>
<th style="text-align: center;">通常充電</th>
<td style="text-align: center;">0x01:充電</td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x00:<br />
出力電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x00</td>
</tr>
<tr>
<th style="text-align: center;">通常放電</th>
<td style="text-align: center;">0x02:放電</td>
<td style="text-align: center;">100</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">&lt;A5&gt;<br />
0x01:<br />
系統電力方式<del>0x00:<br />
出力電力方式</del></td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x00</td>
</tr>
<tr>
<th style="text-align: center;">余剰充電</th>
<td style="text-align: center;">0x01:充電</td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x01:<br />
系統電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x00</td>
</tr>
<tr>
<th style="text-align: center;">自家消費</th>
<td style="text-align: center;">0x03:自家消費</td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x00:<br />
出力電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x00</td>
</tr>
<tr>
<th style="text-align: center;">停止</th>
<td style="text-align: center;"><del><br />
</del>0x00:待機<br />
&lt;A3&gt;</td>
<td style="text-align: center;">100</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x00:<br />
出力電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x00</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（蓄電池➡EV）<br />
(時間優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x05:<br />
</del>0x04:融通<br />
（蓄電池➡EV）<br />
&lt;A６&gt;</strong></td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)<br />
&lt;A6&gt;</td>
<td style="text-align: center;">0<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x:00:定格<br />
&lt;A6&gt;</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（蓄電池➡EV）<br />
(経済優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x05:</del><br />
0x04:融通<br />
（蓄電池➡EV）<br />
&lt;A6&gt;</strong></td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)<br />
&lt;A6&gt;</td>
<td style="text-align: center;">0<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x01:負荷追従<br />
&lt;A6&gt;</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（EV➡蓄電池）<br />
（時間優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x04</del>:<br />
0x05:融通<br />
（EV➡蓄電池）<br />
&lt;A6&gt;</strong></td>
<td style="text-align: center;">100<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x:00:定格<br />
&lt;A6&gt;</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（EV➡蓄電池）<br />
(経済優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x04:<br />
</del>0x05:融通<br />
（EV➡蓄電池）<br />
&lt;A６&gt;</strong></td>
<td style="text-align: center;">100<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※2）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※2）</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">0x01:負荷追従<br />
＜A6＞</td>
</tr>
<tr>
<th style="text-align: left;"><strong>PCSからの読み出し変数（PCS動作状態）</strong></th>
<td style="text-align: center;">42:2052</td>
<td style="text-align: center;">42:2057</td>
<td style="text-align: center;">42:2058</td>
<td style="text-align: center;">42:2059</td>
<td style="text-align: center;">42:205A</td>
<td style="text-align: center;">42:205B</td>
<td style="text-align: center;">C2:110A</td>
<td style="text-align: center;">42:205C</td>
<td style="text-align: center;">C2:110B</td>
<td style="text-align: center;">42:205D</td>
<td style="text-align: center;">C2:110C</td>
<td style="text-align: center;">82:2016</td>
<td style="text-align: center;">42:2067<del>（TBD)<br />
</del>&lt;A13&gt;</td>
</tr>
<tr>
<th style="text-align: center;">備考</th>
<td style="text-align: center;"><del>　</del></td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">　</td>
</tr>
</tbody>
</table>

(※1) GW設定値は実行時刻の充放電スケジュール内値を書き込む。

　　　スマホからの安心充電指令は蓄電池、EVとも共通値となる。

(※2）電力融通指令値時、PCSで参照しない変数を示す。\<A10\>

***

Input欄記載の充放電を実行したい場合は、PCSにOutPut記載の変数（値）を書き込み、動作指令を発行する。

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 5%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 5%" />
</colgroup>
<thead>
<tr>
<th style="text-align: center;">Input<br />
（GWからの充放電設定値）</th>
<th colspan="11" style="text-align: center;">OutPut<br />
（GWからPCSへ設定する充放電指令パラメータ(PCS変数エリア)）</th>
<th style="text-align: center;">　</th>
<th style="text-align: center;">　</th>
<th style="text-align: center;">　</th>
<th style="text-align: center;">　</th>
</tr>
</thead>
<tbody>
<tr>
<th rowspan="3" style="text-align: center;">充放電モード<br />
指令値(※1)</th>
<td colspan="13" style="text-align: center;">蓄電池併設有効時</td>
<td style="text-align: center;">　</td>
<td style="text-align: center;">蓄電池併設充放電指令値が独立時</td>
</tr>
<tr>
<td style="text-align: center;">蓄電池充放電<br />
制御<br />
モード</td>
<td style="text-align: center;">蓄電池<br />
充電目標値<br />
（外部制御）<br />
（GW制御）</td>
<td style="text-align: center;">蓄電池<br />
放電目標値<br />
（外部制御）<br />
（GW制御）</td>
<td style="text-align: center;">蓄電池<br />
安心充電指定</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
充放電方式</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
充放電電力指定</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
充放電電力設定</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
系統電力指定</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
系統電力設定</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
充放電<br />
電力量指定</td>
<td style="text-align: center;">蓄電池<br />
（KPBP)<br />
充放電<br />
電力量設定</td>
<td style="text-align: center;">蓄電池<br />
電力融通モード指定</td>
<td style="text-align: center;">蓄電池<br />
放電停止SOC<br />
(併設時安心モード)<br />
&lt;A5&gt;</td>
<td style="text-align: center;"><del>グリーンモード相当<br />
フラグ</del><br />
夜間充電SOC上限値<br />
固定&lt;A5&gt;</td>
<td rowspan="7" style="text-align: center;">現状の<br />
蓄電池<br />
充放電<br />
に従う</td>
</tr>
<tr>
<td style="text-align: center;">41:205F</td>
<td style="text-align: center;">41:2065</td>
<td style="text-align: center;">41:2066</td>
<td style="text-align: center;">41:2060</td>
<td style="text-align: center;">41:2061</td>
<td style="text-align: center;">41:2062</td>
<td style="text-align: center;">C1:110E</td>
<td style="text-align: center;">41:2063</td>
<td style="text-align: center;">C1:110F</td>
<td style="text-align: center;">41:2064</td>
<td style="text-align: center;">C1:1110</td>
<td style="text-align: center;">41:2068</td>
<td style="text-align: center;"><del>81:2019<br />
</del>81:2030＜A8＞</td>
<td style="text-align: center;"><strong><del>41:2077<br />
</del>41:207B＜A6＞</strong></td>
</tr>
<tr>
<th style="text-align: center;">通常充電</th>
<td style="text-align: center;">0x01:充電</td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x00:<br />
出力電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
</tr>
<tr>
<th style="text-align: center;">通常放電</th>
<td style="text-align: center;">0x02:放電</td>
<td style="text-align: center;">100</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x01:<br />
系統電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
</tr>
<tr>
<th style="text-align: center;">余剰充電</th>
<td style="text-align: center;">0x01:充電</td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x01:<br />
系統電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
</tr>
<tr>
<th style="text-align: center;">自家消費</th>
<td style="text-align: center;">0x03:自家消費</td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x00:<br />
出力電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
</tr>
<tr>
<th style="text-align: center;">停止</th>
<td style="text-align: center;"><del><br />
</del>0x00:待機<br />
&lt;A3&gt;</td>
<td style="text-align: center;">100</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;">0x00:<br />
出力電力方式</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00:OFF</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0x00</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（蓄電池➡EV）<br />
(時間優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x05:<br />
</del>0x04:融通<br />
（蓄電池➡EV）<br />
&lt;A６&gt;</strong></td>
<td style="text-align: center;">100<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x01:<br />
系統電力方式<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;">0x:00:定格</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
<td style="text-align: left;">　</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（蓄電池➡EV）<br />
(経済優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x05:</del><br />
0x04:融通<br />
（蓄電池➡EV）<br />
&lt;A6&gt;</strong></td>
<td style="text-align: center;">100<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
下限SOC(※1)<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;">0x01:負荷追従</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
<td style="text-align: left;">　</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（EV➡蓄電池）<br />
（時間優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x04</del>:<br />
0x05:融通<br />
（EV➡蓄電池）<br />
&lt;A6&gt;</strong></td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">０<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;">0x:00:定格</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
<td style="text-align: left;">　</td>
</tr>
<tr>
<th style="text-align: center;">電力融通<br />
（EV➡蓄電池）<br />
(経済優先）<br />
&lt;A6&gt;</th>
<td style="text-align: center;"><strong><del><br />
0x04:<br />
</del>0x05:融通<br />
（EV➡蓄電池）<br />
&lt;A６&gt;</strong></td>
<td style="text-align: center;">GW設定値<br />
上限SOC(※1)</td>
<td style="text-align: center;">０<br />
&lt;A6&gt;</td>
<td style="text-align: center;">GW設定値<br />
安心設定(※1)</td>
<td style="text-align: center;"><del>0x00:<br />
出力電力方式<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0x00:OFF<br />
</del>任意値（※3）</td>
<td style="text-align: center;"><del>0<br />
</del>任意値（※3）</td>
<td style="text-align: center;">0x01:負荷追従</td>
<td style="text-align: center;">GW設定値<br />
安心設定SOC下限値(※1)</td>
<td style="text-align: center;">夜間充電SOC上限値固定(※2)</td>
<td style="text-align: left;">　</td>
</tr>
<tr>
<th style="text-align: left;"><strong>PCSからの読み出し変数（PCS動作状態）<del>（TBD)<br />
</del>&lt;A13&gt;</strong></th>
<td style="text-align: center;"><strong>42:205F</strong></td>
<td style="text-align: center;"><strong>42:2065</strong></td>
<td style="text-align: center;"><strong>42:2066</strong></td>
<td style="text-align: center;"><strong>42:2060</strong></td>
<td style="text-align: center;"><strong>42:2061</strong></td>
<td style="text-align: center;"><strong>42:2062</strong></td>
<td style="text-align: center;"><strong>C2:110E</strong></td>
<td style="text-align: center;"><strong>42:2063</strong></td>
<td style="text-align: center;"><strong>C2:110F</strong></td>
<td style="text-align: center;"><strong>42:2064</strong></td>
<td style="text-align: center;"><strong>C2:1110</strong></td>
<td style="text-align: center;"><strong>42:2068</strong></td>
<td style="text-align: center;"><strong><del>82:2019<br />
</del>82:2030＜A8＞</strong></td>
<td style="text-align: center;"><strong><del>42:2077</del><br />
42:207B&lt;A2&gt;</strong></td>
<td style="text-align: left;">　</td>
</tr>
<tr>
<th style="text-align: left;">参考：<br />
　KPEPの該当<br />
アドレス</th>
<td style="text-align: center;">42:2052</td>
<td style="text-align: center;">42:2057</td>
<td style="text-align: center;">42:2058</td>
<td style="text-align: center;">41:2059</td>
<td style="text-align: center;">41:205A</td>
<td style="text-align: center;">41:205B</td>
<td style="text-align: center;">C1:110A</td>
<td style="text-align: center;">41:205C</td>
<td style="text-align: center;">C1:110B</td>
<td style="text-align: center;">41:205D</td>
<td style="text-align: center;">C1:110C</td>
<td style="text-align: center;">41:2067</td>
<td style="text-align: center;">81:2016</td>
<td style="text-align: center;">ー</td>
<td style="text-align: left;">　</td>
</tr>
<tr>
<th style="text-align: left;">EP経由で値受領必要</th>
<td style="text-align: left;">　</td>
<td style="text-align: left;">EP経由で値受領必要</td>
<td style="text-align: left;">EP経由で値受領必要</td>
<td style="text-align: left;">EP経由で値受領必要</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">　</td>
<td style="text-align: left;">EP経由で値受領必要</td>
<td style="text-align: left;">EP経由で値受領必要</td>
<td style="text-align: left;">EP経由で値受領必要</td>
<td style="text-align: left;">併設時の充放電変数は使用しない。</td>
</tr>
</tbody>
</table>

(※1) GW設定値は実行時刻の充放電スケジュール内値を書き込む。

(※2) 実行中スケジュールセットIDの設定値を使用する。

外部制御は、PCSからみた”外部”であり、本ケースではGWを示す。

(※3）電力融通指令値時、PCSで参照しない変数を示す。\<A10\>
