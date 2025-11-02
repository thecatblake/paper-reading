## Litechain: A lightweight blockchain for verifiable and scalable federated learning in massive edge networks.
date: 2025-05-06  
categories:   
Edge computing, Blockchain, Federated Learning, Privacy Preservation
### 1. どんなもの？ 
MEN上で効率的にFLをすることのできるBlockchainを開発した。

### 2. 先行研究と比べてどこがすごいの？  
先行研究に比べて、エネルギー消費量が低く、スケールしやすくなっている。

### 3. 技術や手法の"キモ"はどこにある？ 
- 分散型のクラスタリングアルゴリズムを使いMENを階層構造として捉える。
- 処理のアイドル状態を減らすために２回に分けたFLを行う。
- 合意アルゴリズムの定量的なセキュリティーレベルを導出した。
- model identifier を導入しon-chain storageとデータ転送の負担を軽減した。
- 定期的な同期を行うことで、Stale Storageを削減する。

### 4. どうやって有効だと検証した？ 
クラウド上でdockerを使い、独立したノードを再現。CIFAR10をRESNET9で分類するタスクを、
FLC-Model,FLC-Cash,BEFLという先行研究とStorage,Latency,Securityの関連から比較した。

Accuracy over latency:
73.8%を目標とし、どのくらいの時間がかかるかをグラフにした。Litechainが一番効率的に学習ができていることが見てわかる。

Latency overhead:
TT(training task)とVT(verification task)をNetwork内で起こった最大値を棒グラフにして表示。Litechainが一番低いことがわかる。

Storage Evaluation:
on-chain storageがroundを重ねていくごとにどのように変化していくかを表にしている。Litechainは定期的に動機を行っているのでstale storageを削減でき一番効率よくスケーリングができている。

Security Evaluation:
Consensus Securityを論文ないで定量化された式を基に計算して比較している。

Model Protection Performance:
Replay attack, Data poisoning attackに対して、accuracy over latencyのグラフを再度構築している。

### 5. use case
FaaS Federated Learning-as-a-Service
FaaSをBlockchain上に作りutility tokenを発行する。

### 6. 次に読むべき論文はあるか？  

### 論文情報・リンク  
- [著者，"タイトル，" ジャーナル名，voluem，no.，ページ，年

## 再現性
HyperLedger Fabric を使い作られている。
