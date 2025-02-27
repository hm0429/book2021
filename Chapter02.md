# 2章 ブロックチェーンの概要

## 課題

1. 自分にとってのヴァルネラビリティの例を３つ挙げ，それぞれについてそのトラストの構造を分析してください。
1. 上記のトラスト構造を，トラストレスなトラストとして再構成してください。
1. ビットコインのマイニングに対する報酬は，当初１ブロックあたり 50btcでした。これを初期値として210,000 ブロック（約4年）毎にマイニング報酬は半減していきます。

	* ジェネシスブロックのタイムスタンプは，2009-01-04 03:15:05 +0900 です。１ブロックの生成速度を平均10分として，現在の1ブロックあたりのマイニング報酬を求めてください。
	* ビットコインの現在の市場価格（円換算）を調べてください。
	* マイニング用ASICなどの設備投資を無視し，1kWh あたりの電力料金が5円のときと10円のときのマイニング報酬と一致する消費電力量 (kWh) を求めてください。
	* ビットコインの市場価格が現在のまま固定されたときの，40年後のマイニングに要する消費電力量を求めてください。


### 1. 自分にとってのヴァルネラビリティの例を３つ挙げ，それぞれについてそのトラストの構造を分析してください。

#### 分析の視点

* 自分や大切な人の身体や生存への危険，経済的損失，人間関係の毀損，社会的地位の毀損，尊厳の毀損，思想信条や宗教の侵害，病歴学歴犯罪歴経済状態など個人データの漏洩
* 自分がかつて感じたことがある具体的な自分のヴァルネラビリティへの侵害の例を考えてみましょう
* そのような自分のヴァルネラビリティを託することが可能な主体の例を考えてみましょう
* ヴァルネラビリティを託する主体がとり得る行動とその利得をゲーム理論的に利得表として分析してみましょう

#### トラストの構造の分析方法

上記の分析を元に以下の内容を整理してみましょう。

* ヴァルネラビリティ（自分では制御できないもの）
* トラストの対象の例（信頼できる第三者）
* トラストの対象に期待する行動

### 2. 上記のトラスト構造を，トラストレスなトラストとして再構成してください。

* それぞれのヴァルネラビリティをトラストレスなトラストによって実現しようとするとき，必要となる「審判」としての行動はどのような処理になるでしょうか
* 審判は誰か？審判の行為とそのゲーム理論的分析

* 「トラストの対象」となるいかなる主体も存在しないことが前提です
* ネットワークシステムには全体として「審判」としての機能が備わっているものとします。
* 「トラストの対象による重要な行為への期待」と同等なことが「審判」によって実現できるための条件を分析してください

### 3. ビットコインのマイニングに対する報酬は，当初１ブロックあたり 50btcでした。これを初期値として210,000 ブロック（約4年）毎にマイニング報酬は半減していきます。

(1)  ジェネシスブロックのタイムスタンプは，2009-01-04 03:15:05 +0900 です。１ブロックの生成速度を平均10分として，現在の1ブロックあたりのマイニング報酬を求めてください。

```ruby
 reward=50*(0.5**(((Time.now-Time.new(2009,1,4,3,15,5,'+09:00'))/(600*210000)).floor))

# 2021年７月２日時点で 6.25 BTC
```

(2) ビットコインの現在の市場価格（円換算）を調べてください。

Blockchain.comのAPIを利用した例

```ruby
require 'net/http'
require 'json'

btc=JSON.parse(Net::HTTP.get(URI.parse('https://blockchain.info/tickers')).gsub("\n",''))
btc_jpy=btc["BTC"]["JPY"]["last"]

# 2021年７月２日時点で　3676342.41円
```

(3) マイニング用ASICなどの設備投資を無視し，1kWh あたりの電力料金が5円のときと10円のときのマイニング報酬と一致する消費電力量 (kWh) を求めてください。


```ruby
# 10分あたりの電力で評価
# 5円／1KWh のときの10分あたりの単価
unit=5.0/6
# 消費電力料（TWh）
twh=(btc_jpy*reward/unit)/1000000

# 2021年7月2日現在 27.572568075 TWh

# 10円／1KWh のときの10分あたりの単価
unit=10.0/6
# 消費電力料（TWh）
twh=(btc_jpy*reward/unit)/1000000

# 2021年7月2日現在　13.7862840375 TWh

# ただし，この消費量はマイニング競争に参加する一つのプレーヤーが費やす電力
```

(4) ビットコインの市場価格が現在のまま固定されたときの，40年後のマイニングに要する消費電力量を求めてください。
	
```ruby
N=40
reward2=50*(0.5**((((Time.now+365.25*24*60*60*N)-Time.new(2009,1,4,3,15,5,'+09:00'))/(600*210000)).floor))

# 5円／1KWh のときの10分あたりの単価
unit=5.0/6
# 消費電力料（TWh）
twh=(btc_jpy*reward2/unit)/1000000

# 2021年の40年後2061年　0.026926　TWh

# 10円／1KWh のときの10分あたりの単価
unit=10.0/6
# 消費電力料（TWh）
twh=(btc_jpy*reward2/unit)/1000000

# 2021年の40年後2061年　0.01346　TWh

```

