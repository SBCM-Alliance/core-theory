# Mathematical Specification for SBCM
**A Field-Theoretic Approach to Regional Economics and Administrative Dynamics**

**Version:** 1.0  
**Author:** Melnus (SBCM Alliance)

---

## 1. 基礎単位の定義 (Fundamental Units)

SBCMは、国家を均質な全体ではなく、離散的な「標準ブロック」の集合体として定義する。

### 1.1 標準ブロック ($B_{std}$)
日本の統治構造における最小の自律単位。

$$
B_{std} = \frac{P_{total}}{N_{muni}} \approx 72,176 \quad [\text{persons}]
$$

*   $P_{total}$: 総人口 ($1.24 \times 10^8$)
*   $N_{muni}$: 基礎自治体数 ($1,718$)

### 1.2 自治体規模係数 ($S_{factor}$)
対象自治体 $i$ の人口 $P_i$ が、標準ブロック何個分に相当するかを示すスカラー量。

$$
S_{factor}(i) = \frac{P_i}{B_{std}}
$$

---

## 2. 静的評価指標 (Static Evaluation Metrics)

ある時点 $t$ における施策 $k$ の健全性を評価するための指標。

### 2.1 インパクト係数 ($I$)
$$
I_{budget} = \frac{C_k}{U_{std} \cdot S_{factor}(i)}, \quad I_{coverage} = \frac{V_k}{B_{std}}
$$

*   $C_k$: 施策 $k$ の予算額 [JPY]
*   $U_{std}$: 標準予算単位 (例: $1.0 \times 10^7$ JPY)
*   $V_k$: 受益者数 [persons]

### 2.2 予算歪み指数 ($D_{index}$)
予算投入量と普及効果の比率。

$$
D_{index} = \frac{I_{budget}}{I_{coverage}}
$$

*   **判定基準:**
    *   $D_{index} \approx 1$: 適正 (Normal)
    *   $D_{index} \gg 10$: 構造的歪み (Distortion / 監査対象)

---

## 3. 動的支配方程式 (Dynamic Governing Equation)

地域経済を「富の流体」と見なし、物理学における**連続の式 (Equation of Continuity)** を適用する。

### 3.1 SBCM支配方程式
座標 $\mathbf{x}$ における経済密度 $\rho$ の時間発展は、以下の偏微分方程式で記述される。

$$
\frac{\partial \rho}{\partial t} + \nabla \cdot \mathbf{J} = \sigma
$$

ここで、
*   $\rho(\mathbf{x}, t)$: **経済密度** (Economic Density / 富や活力の蓄積量)
*   $\mathbf{J}(\mathbf{x}, t) = \rho \mathbf{v}$: **経済流束ベクトル** (Economic Flux)
    *   $\mathbf{v}$: 富の移動速度ベクトル
*   $\sigma(\mathbf{x}, t)$: **生成・消滅項** (Source / Sink)

### 3.2 項の物理的解釈

#### (1) 時間変化項 $\frac{\partial \rho}{\partial t}$
*   地域の成長率または衰退率。
*   **生存条件:** $\frac{\partial \rho}{\partial t} \ge 0$

#### (2) 移流項 (ダイバージェンス) $\nabla \cdot \mathbf{J}$
*   富の空間的な流出入を表す。
*   $\nabla \cdot \mathbf{J} > 0$ (発散): 富が外部へ流出している状態 (**ストロー効果**)。
*   $\nabla \cdot \mathbf{J} < 0$ (収束): 富が内部へ蓄積・循環している状態。

#### (3) 生成・消滅項 $\sigma = S - L$
*   $S$ (Source): 内部での価値生産 (Yorbeeによる労働、Sonaによるエネルギー生産)。
*   $L$ (Loss): システム維持費、中抜きによる散逸、インフラ老朽化コスト。

---

## 4. ストロー効果の数理モデル (Mathematical Model of Leakage)

移流項 $\nabla \cdot \mathbf{J}$ を制御するパラメータとして、**漏出率 (Leakage Rate, $\lambda$)** を定義する。

$$
\lambda = f\left( \frac{I_{budget}}{C_{capacity}} \right)
$$

*   $I_{budget}$: プロジェクトの予算規模
*   $C_{capacity}$: 地域内事業者の最大受注キャパシティ

### 定理：大規模発注による富の漏出
プロジェクト規模が地域キャパシティを超過する場合、漏出率は1に収束する。

$$
\lim_{I_{budget} \gg C_{capacity}} \lambda \to 1.0
$$

*   **解釈:** 巨大公共事業は、地域経済への波及効果が物理的にゼロになる。
*   **対策 (G-Cart):** アルゴリズムにより $I_{budget}$ を分割し、$I_{budget} \le \sum C_{local}$ とすることで、$\lambda \to 0$ (地域内循環) を実現する。

---

## 5. 最適化目標 (Optimization Targets)

SBCMエコシステムの目的は、以下の汎関数を最大化することである。

$$
\text{Maximize } \int_{Area} \left( S(\mathbf{x}) - L(\mathbf{x}) - \nabla \cdot \mathbf{J}(\mathbf{x}) \right) d\mathbf{x}
$$

すなわち、
1.  **Sourceの最大化:** Yorbee/Sonaによる価値生産。
2.  **Lossの最小化:** 中抜き・インフラ維持費の削減。
3.  **Divergenceの最小化:** ストロー効果の阻止と、地域内循環 ($R_{block}$) の向上。
