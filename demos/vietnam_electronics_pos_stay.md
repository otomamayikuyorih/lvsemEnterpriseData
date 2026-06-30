# Demo 2: 電子産業における組織支援、職務満足、WLB、定着意図

## データ

- Dataset ID: `vietnam_electronics_pos_stay`
- Source: https://data.mendeley.com/datasets/pyjkvgjmfz/2
- License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/)
- 分析に使った有効行数: 604
- ブートストラップ回数: 300

## モデル

`POS` が職務満足とワークライフバランスを高め、それらが定着意図に影響するモデルです。

### 測定ブロック

- `POS`: `POS1`, `POS2`, `POS3`, `POS4`, `POS5`, `POS6`, `POS7`, `POS8`
- `JS`: `JS1`, `JS2`, `JS3`, `JS4`, `JS5`
- `WLB`: `WLB1`, `WLB2`, `WLB3`
- `ITS`: `ITS1`, `ITS2`, `ITS3`, `ITS4`, `ITS5`

### 構造パス

- `POS` -> `JS`
- `POS` -> `WLB`
- `POS` -> `ITS`
- `JS` -> `ITS`
- `WLB` -> `ITS`

## 信頼性・妥当性の要約

```text
 block alpha composite_reliability   ave
   POS 0.911                 0.928 0.617
    JS 0.850                 0.893 0.625
   WLB 0.759                 0.861 0.674
   ITS 0.879                 0.912 0.674
```

### ローディング要約

```text
 block min_loading mean_loading max_loading items
   ITS       0.800        0.821       0.851     5
    JS       0.748        0.790       0.833     5
   POS       0.757        0.785       0.818     8
   WLB       0.807        0.821       0.843     3
```

## 構造モデル

### パス係数

```text
       path  beta
  POS_to_JS 0.626
 POS_to_WLB 0.525
 POS_to_ITS 0.478
  JS_to_ITS 0.139
 WLB_to_ITS 0.280
```

### ブートストラップ

```text
       path  beta boot_se t_value p_value_approx
  POS_to_JS 0.626   0.043  14.547          0.000
 POS_to_WLB 0.525   0.048  10.960          0.000
 POS_to_ITS 0.478   0.060   7.919          0.000
  JS_to_ITS 0.139   0.052   2.674          0.008
 WLB_to_ITS 0.280   0.045   6.179          0.000
```

### R2

```text
 construct r_squared
        JS     0.392
       WLB     0.276
       ITS     0.603
```

## メモ

- このデモは `lvsem` の軽量ワークフローに合わせ、測定項目から潜在変数スコアを作成し、構造パスを標準化回帰として推定しています。
- 欠損や非数値は、指定した測定項目を数値化したうえで完全ケースのみを使いました。
- 研究論文の厳密な再現ではなく、`lvsemEnterpriseData` に収録した企業・組織内データの利用例です。

