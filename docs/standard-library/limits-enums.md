---
description: '詳細情報: &lt; 制限の &gt; 列挙型'
title: '&lt;limits&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 115122a4901298018df8809be56a7fc69249d700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312866"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt; 列挙型

## <a name="float_denorm_style"></a><a name="float_denorm_style"></a> float_denorm_style

この列挙体では、小さすぎて、正規化された値としては表現できない非正規化された浮動小数点値を表現するために、実装で選択できるさまざまなメソッドを記述します。

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>戻り値

この列挙型は以下を返します。

- `denorm_indeterminate` 変換時に非正規化された形式が存在するかどうかを判断できない場合は。

- `denorm_absent` 非正規化形式が存在しない場合。

- `denorm_present` 非正規化された形式が存在する場合。

### <a name="example"></a>例

この列挙型の値にアクセスする例については、「[numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm)」を参照してください。

## <a name="float_round_style"></a><a name="float_round_style"></a> float_round_style

この列挙体では、浮動小数点値を整数値に丸めるために、実装で選択できるさまざまなメソッドを記述します。

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>戻り値

この列挙型は以下を返します。

- `round_indeterminate` 丸め方法を決定できない場合は。

- `round_toward_zero` を0方向に丸める場合は。

- `round_to_nearest` が最も近い整数に丸められる場合は。

- `round_toward_infinity` が0から離れる場合は。

- `round_toward_neg_infinity` 負の整数に丸められる場合は。

### <a name="example"></a>例

この列挙型の値にアクセスする例については、「[numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style)」を参照してください。
