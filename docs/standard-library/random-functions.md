---
title: '&lt;random&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 87b640d4f3aa3fbfa23ad5603d84102301e71ea4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240381"
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt; 関数

## <a name="generate_canonical"></a> generate_canonical

ランダム シーケンスから浮動小数点値を返します。

> [!NOTE]
> ISO C++ 標準では、この関数は範囲 [ `0`, `1`) 内の値を返すと述べられています。 Visual Studio は、まだこの制約には準拠していません。 この範囲内の値を生成する代替手段として、[uniform_real_distribution](../standard-library/uniform-real-distribution-class.md) を使用します。

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>パラメーター

*RealType*\
浮動小数点整数型。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。

*Bits*\
乱数ジェネレーター。

*汎用*\
乱数ジェネレーター。

### <a name="remarks"></a>Remarks

テンプレートの関数呼び出し`operator()`の*Gen*繰り返しと返される値を浮動小数点値にパック`x`型の*RealType*まで、指定した数を収集しました仮数部のビットの`x`します。 指定した数がのうち、小さい方*ビット*(0 以外の値がある必要があります) と仮数部のビット数の完全な*RealType*します。 最初の呼び出しで最下位のビットが提供されます。 `x` が返されます。
