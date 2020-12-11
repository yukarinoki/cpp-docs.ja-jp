---
description: 詳細については、「 &lt; random 関数」を参照してください。 &gt;
title: '&lt;random&gt; 関数'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 39670fcd9b200a6bd56656bbfa07391fdd0d96be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163341"
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt; 関数

## <a name="generate_canonical"></a><a name="generate_canonical"></a> generate_canonical

ランダム シーケンスから浮動小数点値を返します。

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>パラメーター

*RealType*\
浮動小数点整数型。 使用できる型については、「」を参照してください [\<random>](../standard-library/random.md) 。

*列*\
使用するランダムなビット数。

*ジェネレーター*\
乱数ジェネレータークラス。

*世代*\
型 *ジェネレーター* の乱数ジェネレーターのインスタンスへの参照。

### <a name="remarks"></a>解説

このテンプレート関数は `operator()` 、 *ジェネレーション* のを繰り返し呼び出し、返された値を、指定し `x` た数の仮数ビットがに収集されるまで、 *realtype* 型の浮動小数点値にパックし `x` ます。 指定された数値は、(0 以外である必要がある) *ビット* の小さい方で、 *realtype* の仮数部のビット数が完全ではありません。 最初の呼び出しで最下位のビットが提供されます。 `x` が返されます。
