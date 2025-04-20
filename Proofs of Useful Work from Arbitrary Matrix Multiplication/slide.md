---
marp: true
theme: default
---

# PoWを「意味のある労働」へ
## 行列演算(MatMul)を用いたPoUWの提案

---

# 既存PoWの問題点

- Proof of Work (PoW) は膨大な計算リソースを消費
- 多くの場合、その計算自体に直接的な社会的価値はない
- **エネルギーの無駄遣い**という批判

---

# 提案：Proof of Useful Work (PoUW)

- PoWの計算を **「意味のある労働」** に変える新しい概念
- 本論文では、**行列演算 (MatMul)** を計算タスクとして採用することを提案[2][5][7]

**なぜMatMulなのか？**
- AI（特に深層学習）の学習や推論で **計算負荷の大部分を占める**[4]
- AIモデルの性能に直結する重要な演算[4]

---

# MatMul導入によるメリット

- **エネルギー効率の向上**: PoWの計算が無駄にならず、AI関連タスクに活用される
- **AIの発展に貢献**:
    - AIモデルの **学習 (Training)**[8][19]
    - AIモデルの **推論 (Inference)**[8][12][14][16]
- これらの計算リソースを提供することで、AI分野全体の進歩を加速させる可能性[10]

---

# 歴史的背景：スパムメール対策としての誕生

- **起源**: 1992年 (論文は1993年)、Cynthia Dwork と Moni Naor らによって提唱[1]
- **目的**: メール送信者に**意図的に計算負荷（Work）**を課す
    - 計算には一定の難易度と時間が必要
    - スパムメール送信のコストを高め、大量送信を抑止[1]
- この「計算の証明 (Proof)」が **Proof of Work (PoW)** の原型となった[1]

---

# 問題点１：膨大なエネルギー消費

- PoWの計算には **膨大な電力** が必要[9][18]
- **環境への影響** が懸念されている[9][12]
    - 例：ビットコインのPoWは、年間で **世界の電力消費量の約0.5%** に相当する電力を消費するという推計もある[18]
    - (ユーザー提供情報：アメリカの年間電気消費量の2%に匹敵するとも言われる)

---

# 問題点２：計算自体の「無価値」性

- PoWで行われる計算（例: ハッシュ計算）は、**それ自体が社会的に有用な価値を生み出すものではない**[7]
- 計算の目的は、あくまでネットワークのセキュリティ維持や合意形成の手段[7][16]

> Finally, the evaluation of the pricing function serves no useful purpose, except serving as a deterrent. It would be exciting to come up with a scheme in which evaluating the pricing function serves some additional purpose.
>
> _(Dwork & Naor, 1993年の論文より)_


---

# PoUWについて (Proof of Useful Work)

---

# PoW が「Useful (有用)」になるための条件

PoWシステムが単なる計算証明を超え、「有用」であるとみなされるためには、一般的に以下の3つの主要な特性を満たす必要があると考えられています[4][5]。

- **経済的価値 (Economic Value)**
    - マイナーが行う計算結果に現実的な需要が存在し、誰かがその結果に対価を支払う意思があること[4][5]。
- **効率性 (Efficiency)**
    - 問題を解決するために使用されるアルゴリズムが、ほぼ最適であること[4][5]。計算プロセス自体に無駄が少ないこと[5]。
- **セキュリティ (Security)**
    - システムの安全性が PoW と同等レベルで保証されていること（例：二重支払い攻撃への耐性）[4][5]。

---

# PoUW実現の難しさ：過去の課題

- **理論構築の困難**: PoUW の具体的な理論的構築自体が長年困難（elusive）であったとされています (ユーザー提供情報)。
- **マイナーの選択**: 特に、マイナー自身が**任意の「有用な」タスクインスタンスを選択できる**ような、真に実用的な PoUW の提案はこれまで知られていませんでした 。
    - 過去の提案では、正直な証明者（マイナー）が単一インスタンスの解決を検証者に納得させるために、多数の異なるインスタンスを解く必要があり、効率性の要件を満たせないケースがありました[4]。

---

# 「無駄のない」マイニングシステムの探求

- **"Proofs of Useless Work"**: Maya Dotan と Saar Tochner による研究[2][5]では、「無駄のない (wasteless)」PoW システムに必要な特性（有用性、効率性、セキュリティ）を形式的に定義し、分析しました[2][5]。
    - この研究は、PoUW が満たすべき制約を明らかにしようと試みました[2]。
    - 「有用な」問題を「ユーザーが対価を支払う意思のある問題」と定義し、経済的インセンティブの重要性を指摘しています[5]。
    - また、マイナーがシステム外部ではなく、**システム内部で問題を解くインセンティブ**をどう設計するかが課題であることも示唆しています[5]。

---

# PoUWへの期待：Ethereum開発者の視点

Ethereum の共同創設者 Vitalik Buterin は、PoUW の可能性について以下のように述べています (ユーザー提供情報, [4])。

> “If either an efficiently verifiable proof-of-computation for Folding@home
can be produced, or if we can find some other useful computation which is
easy to verify, then cryptocurrency mining could actually become a huge boon
to society, not only removing the objection that Bitcoin wastes "energy",
but even being socially beneficial by providing a public good."

これは、検証の容易さが PoUW 実現の鍵であり、成功すればエネルギー問題の解決と社会貢献の両方を達成できる可能性を示唆しています。


