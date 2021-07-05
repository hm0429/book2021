# 3章 演習

## 演習課題
1. 不特定のメンバーによる賭け事をスマートコントラクトで実現するとき，そのオラクル（賭けの結果）がすべてのメンバーから見て信用できるものになるための「分権的な」トラスト構造を提案してください。
1. スピード違反への自動罰金引き落としの例について，政府によるスマートコントラクトに対する統治される側からの安全装置の構成方法を提案してください。
1. 不特定のメンバーによる賭け事のシステムを，掛け金をトークンとし，賭ける対象をトークンの送金先アドレスとし，結果をトークンの状態遷移として表現する方法で構成してみてください。また，このときオラクル（賭けの結果）のトラストはどのように構成すべきでしょうか。
1. ニック・サボの論文を読んでください。
1. Ethereumのwhite paperを読んでください。
1. 4章を学ぶための前提として数学の知識が必要となります。付録の数学的基礎をすべて読んでください。


###  1. 不特定のメンバーによる賭け事をスマートコントラクトで実現するとき，そのオラクル（賭けの結果）がすべてのメンバーから見て信用できるものになるための「分権的な」トラスト構造を提案してください。

#### 提案のポイント

* 報道されるスポーツの試合結果や公共ギャンブルのレース結果は信頼できる第三者によってオラクルが提供されます
* 賭け事の直接の結果（オラクル）が信頼できない場合についてトラストの構造を考えてください
* 分権的であるとは，すべての当事者が他の誰かに判断を求めずに自分で判断することです
* 賭けの結果を偽るとゲーム理論的な利得が不利になるような状況を設計してみましょう
* ゲーム理論的状況には審判として振る舞う主体の存在が鍵になるでしょう
* 時間経過や不正発覚による資金の払い戻しをスマートコントラクトの条件に含むことを検討してみましょう


### 2. スピード違反への自動罰金引き落としの例について，政府によるスマートコントラクトに対する統治される側からの安全装置の構成方法を提案してください。

#### 提案のポイント

* ギャンブルのシステムを参考に，スピード違反者の罰金の支払いを行うスマートコントラクトとオラクルを設計してみましょう
* スピード違反を検出し，オラクルとしてスマートコントラクトに通知するシステムを設計してみましょう
* スピード違反というオラクルに対する審判として振る舞う主体を設計してみましょう
* 提案システムにおいて，立法，司法，行政にあたる機能が，分権化されているか分析してみましょう
* すでに稼働しているスマートコントラクトに不備が見つかった場合，どのような方法で不備の存在を確定し，適切な仕様を設計し，修正されるべきでしょうか。
* また不備があるスマートコントラクトによって支払い済の罰金はどのようにして回収すべきでしょうか

### 3. 不特定のメンバーによる賭け事のシステムを，掛け金をトークンとし，賭ける対象をトークンの送金先アドレスとし，結果をトークンの状態遷移として表現する方法で構成してみてください。また，このときオラクル（賭けの結果）のトラストはどのように構成すべきでしょうか。

#### 提案のポイント

* まず 1. で提案した信頼できる第三者が存在しない賭け事を適用してみてください
* トークンの発行者とトークンを使う参加者のゲーム理論的利得を分析してみてください
* オラクルに対する審判として振る舞う主体を設計してみてください
* 賭けの結果（オラクル）によるトークンの状態遷移を設計してください
* トークンのライフサイクル（発行から消滅までの過程と実施主体）を設計してください
* 設計したシステムにおいてトークンはどのような意味と機能を持っているでしょうか

### 4. ニック・サボの論文を読んでください。

[https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart_contracts_2.html)

### 5. Ethereumのwhite paperを読んでください。

[https://ethereum.org/en/whitepaper/](https://ethereum.org/en/whitepaper/)


### 6. 4章を学ぶための前提として数学の知識が必要となります。付録の数学的基礎をすべて読んでください。

登場するすべてのアルゴリズムを実装してみてください。

[実装例](./appendix.md)