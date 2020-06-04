---
title: '&lt;limits&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425611"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt; 列挙型

## <a name="float_denorm_style"></a>float_denorm_style

この列挙体では、小さすぎて、正規化された値としては表現できない非正規化された浮動小数点値を表現するために、実装で選択できるさまざまなメソッドを記述します。

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>戻り値

この列挙型は以下を返します。

- 変換時に非正規化されたフォームの有無を判断できない場合に `denorm_indeterminate` します。

- 非正規化形式が存在しない場合に `denorm_absent` します。

- 非正規化形式が存在する場合は `denorm_present` します。

### <a name="example"></a>例

この列挙型の値にアクセスする例については、「[numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm)」を参照してください。

## <a name="float_round_style"></a>float_round_style

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

- 丸め方法を決定できない場合は `round_indeterminate` します。

- を0方向に丸める場合は `round_toward_zero` します。

- が最も近い整数に丸める場合は `round_to_nearest` します。

- が0から離れる場合に `round_toward_infinity` します。

- 負の整数に丸められた場合は `round_toward_neg_infinity` します。

### <a name="example"></a>例

この列挙型の値にアクセスする例については、「[numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style)」を参照してください。
