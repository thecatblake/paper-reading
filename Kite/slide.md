---
marp: true
title: Kite: How to Delegate Voting Power Privately
author: Kamilla Nazirkhanova, Vrushank Gunjur, X. Pilli Cruz-De Jesus, Dan Boneh
paginate: true
theme: default
---

# Kite: How to Delegate Voting Power Privately

- プライバシーを保ったままの投票権委任プロトコル
- DAOガバナンスにおける課題に対応
- Ethereumベースで実装・評価済

---

## 背景：問題点と動機

- 現在のDAO投票システム：
  - プライベートな投票は可能でも、委任は公開される
  - 代表者（Delegate）の履歴も公開
- 改善点：
  - 委任の**匿名性**
  - 投票自体もプライベートに可能

---

## Kiteの特徴

- **完全匿名の委任**
  - 誰が誰に委任したか一切分からない
- **公開/非公開投票**の両方に対応
- **Zero-Knowledge Proof (ZK)** を活用

---

## 構成要素、、

- Voter（投票者）
- Delegate（代理投票者）
- Trusted Authority（信頼できる集計者）
- Smart Contract（Ethereum上の実装）

---

## 技術要素

- Homomorphic Encryption
- Merkle Tree
- zkSNARK（Noirによる実装）
- ERC-20ロック機構

---

## ZKPの役割

🛡️ KiteでZKPを使う目的
委任時	「1人にだけ委任している」「トークン量は正しい」	誰に委任したか
投票時	「有効な候補に投票している」「重複していない」	どの候補に投票したか（非公開投票時）
登録確認	「私は登録済みである」	登録者リストの中身や他人の情報

---

## 既存の手法との比較：MACI vs Kite

|項目|MACI|Kite|
|---|---|---|
|主な目的|**買収・共謀耐性（anti-collusion）**|**匿名委任と匿名投票の実現**|
|対応する投票者行動|直接投票のみ|**委任＋直接投票両対応**|
|委任先の匿名性|❌（そもそも委任不可）|✅ 委任先にも知られない|
|ゼロ知識証明の使い方|投票の正当性と非重複性の証明|委任と投票の**構造的正当性の証明**|
|集計の形式|信頼できる coordinator が必要|信頼された集計者（Trusted Authority）による復号|
---

## 貢献と関連研究との違い

- 委任先が誰から委任されたかを**一切知ることがない**
- **匿名通信チャネル不要**
- **スマートコントラクトによる完全実装あり**

---

## まとめ

- KiteはDAOの透明性とプライバシーのバランスを実現
- 実装・理論両面から評価済み
- プライベートなガバナンスの未来に貢献

---

## 参考リンク

- [論文ページ (arXiv)](https://arxiv.org/abs/2501.05626)
- [Noir zkSNARK Framework](https://noir-lang.org/)
- [Nouns DAO 投票の議論](https://discourse.nouns.wtf/t/small-grants-zk-private-voting-for-nouns-dao/3405)
