---
description: '詳細情報: subtract_with_carry_engine クラス'
title: subtract_with_carry_engine クラス
ms.date: 11/04/2016
f1_keywords:
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
helpviewer_keywords:
- std::subtract_with_carry_engine [C++]
- std::subtract_with_carry_engine [C++], default_seed
- std::subtract_with_carry_engine [C++], discard
- std::subtract_with_carry_engine [C++], min
- std::subtract_with_carry_engine [C++], max
- std::subtract_with_carry_engine [C++], seed
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
ms.openlocfilehash: 9d2c082f2c7b8405cf8cd25bce6a77d263fd8f64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183387"
---
# <a name="subtract_with_carry_engine-class"></a>subtract_with_carry_engine クラス

キャリー付き減算 (ラグ付きフィボナッチ法) アルゴリズムでランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>パラメーター

*UIntType*\
結果を表す符号なし整数型。 使用できる型については、「」を参照してください [\<random>](../standard-library/random.md) 。

*リダイレクト*\
**ワード サイズ**。 状態シーケンスの各ワードのサイズ (ビット数)。 **前提条件**: `0 < W ≤ numeric_limits<UIntType>::digits`

*2$s*\
**短いラグ**。 整数値の数。 **前提条件**: `0 < S < R`

*\R\n\r\n*\
**長いラグ**。 生成される数列の中の繰り返しを決定します。

## <a name="members"></a>メンバー

`subtract_with_carry_engine::subtract_with_carry_engine`
`subtract_with_carry_engine::max`\
`subtract_with_carry_engine::min`\
`subtract_with_carry_engine::discard`\
`subtract_with_carry_engine::operator()`\
`subtract_with_carry_engine::seed`

`default_seed` は、`19780503u` として定義されているメンバー定数で、`subtract_with_carry_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。

エンジンメンバーの詳細については、「」を参照してください [\<random>](../standard-library/random.md) 。

## <a name="remarks"></a>解説

`substract_with_carry_engine`クラステンプレートは、 [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md)を改善したものです。 これらのエンジンはいずれも、[mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md) ほど高速ではなく、結果も高品質ではありません。

このエンジンは、繰り返しの関係 ( *period*) を使用して、ユーザー指定の符号なし整数型の値を生成します。この場合、の `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M` 場合は `cy(i)` 値が、 `1` `x(i - S) - x(i - R) - cy(i - 1) < 0` それ以外の場合は値が `0` `M` `2` <sup>W</sup>になります。エンジンの状態は、キャリーインジケーターと *R* の値を加算したものです。 これらの値は、が r 回以上呼び出された場合に返される最後の *r* 値、それ以外の場合は `operator()`  `N` 返された値、およびシードの最後の値で構成され `R - N` ます。

テンプレート引数 `UIntType` には、最大 `M - 1` の値を保持するのに十分な大きさが必要です。

このエンジンから直接ジェネレーターを構築できますが、定義済みの typedef のいずれかを使用することもできます。

`ranlux24_base`: `ranlux24` のベースとして使用されます。
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: `ranlux48` のベースとして使用されます。
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

キャリー付き減算エンジンのアルゴリズムの詳細については、Wikipedia の記事「[Lagged Fibonacci generator](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator)」(Lagged Fibonacci 法) を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:**\<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)
