---
marp: true
theme: default
class: lead
paginate: true
---

# Epass: Efficient and Privacy-Preserving Asynchronous Payment on Blockchain

著者: Weijie Wang ほか  
発表: arXiv:2506.09387v1 (2025年6月)  
テーマ: BNPL × ブロックチェーン × プライバシー保護

---

## どんなもの？

- BNPL（Buy Now Pay Later）をブロックチェーン上で非同期的に実現する方式
- 従来のスマートコントラクトベースのBNPLでは **取引の透明性によるプライバシー問題** や **スケーラビリティの低下** が問題
- 提案方式「Epass」は以下を実現：
  - ユーザ取引のプライバシー保護
  - 新規トランザクション生成を抑制してスケーラビリティ向上

---

## 先行研究と比べてどこがすごい？

| 手法 | プライバシー保護 | スケーラビリティ |
|------|------------------|------------------|
| PLP / Atpay / Apenow | ✗（スマコンで全公開） | ✗（取引数が多くなる） |
| LVS（Locally Verifiable Signatures）| △（単一検証） | △（検証が多い） |
| **Epass** | ✅ 署名集約・再暗号化 | ✅ トランザクション書き換えで済む |

---

## 技術や手法のキモはどこ？

- **ローカル検証可能な署名**（Locally Verifiable Signature）を集約し、プライバシー保護
- **カメレオンハッシュ** を用いたブロック書き換え
- **Timed-Release Encryption** により、特定時間にのみ書き換えを許可
- **Redactable Blockchain** により、新規トランザクションを生成せず変更可能

---

## どうやって有効だと検証した？

- 実験環境: Java + JPBC + Geth（Go-Ethereum）で実装
- 検証指標:
  - 時間コスト：従来のLVSやGethと比較して約1/4に短縮
  - 通信コスト：最大50KB以下（ユーザ数32、遅延取引24件）
  - スケーラビリティ：トランザクション2000件でGethの6秒に対してEpassは1秒以下
- セキュリティ証明:
  - IND-CPA（暗号強度）
  - EU-CMA（署名の偽造耐性）

---

## 議論はある？

- **TIKを提供するサーバ（セミトラスト）への信頼依存**
- CA（証明局）を完全信頼と仮定
- 処理複雑性：高度な暗号処理が含まれるため、軽量デバイス向けには要検討

---

## 次に読むべき論文は？

- [Locally Verifiable Signature and Key Aggregation (Goyal & Vaikuntanathan, 2022)](https://eprint.iacr.org/2022/1385)  
  → 本論文の署名技術の基礎

- [Chameleon Hash and Signatures (Krawczyk & Rabin, 1998)]  
  → ブロック改変技術の基礎

- [Timed-release encryption (Di Crescenzo et al., 1999)]  
  → 時間制限付き暗号の理論的基盤

---

## まとめ

- Epassは、ブロックチェーン上のBNPLにおいて、**プライバシーと効率性を両立**
- トランザクションの書き換え方式により、従来のスケーラビリティ問題を回避
- 実用的なセキュリティと通信コストを実験で確認済み
- プライバシー重視のWeb3決済技術として今後の発展が期待される

