---
title: linear_congruential_engine クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::linear_congruential_engine
dev_langs:
- C++
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f902e7a1a3ae4bcb35a4822228425747476d5bc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="linearcongruentialengine-class"></a>linear_congruential_engine クラス

線形合同法アルゴリズムでランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
class linear_congruential_engine{
   public:  // types
   typedef UIntType result_type;
   // engine characteristics
   static constexpr result_type multiplier = a;
   static constexpr result_type increment = c;
   static constexpr result_type modulus = m;
   static constexpr result_type min() { return c == 0u  1u: 0u; }
   static constexpr result_type max() { return m - 1u; }
   static constexpr result_type default_seed = 1u;
   // constructors and seeding functions
   explicit linear_congruential_engine(result_type s = default_seed);
   template <class Sseq>
   explicit linear_congruential_engine(Sseq& q);
   void seed(result_type s = default_seed);
   template <class Sseq>
   void seed(Sseq& q);
   // generating functions
   result_type operator()();
   void discard(unsigned long long z);
   };
```

### <a name="parameters"></a>パラメーター

`UIntType` 結果の型が符号なし整数。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。

`A` **乗数**です。 **Precondition**: セクションの「解説」を参照してください。

`C` **インクリメント**です。 **Precondition**: セクションの「解説」を参照してください。

`M` **剰余**です。 **Precondition**:「解説」を参照してください。

## <a name="members"></a>メンバー

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed` は、`1u` として定義されているメンバー定数で、`linear_congruential_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>コメント

`linear_congruential_engine` テンプレート クラスは、最も単純なジェネレーター エンジンですが、速度や品質は最高というわけではありません。 このエンジンを改良したものが [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md) です。 これらのエンジンはいずれも、[mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md) ほど高速ではなく、結果も高品質ではありません。

このエンジンは、漸化式 ( *周期*) `x(i) = (A * x(i-1) + C) mod M` を使用して、ユーザー指定の符号なし整数型の値を生成します。

`M` が 0 の場合、この剰余演算に使用される値は `numeric_limits<result_type>::max() + 1` です。 エンジンの状態は、最後に返された値か、または `operator()` に対して呼び出しが行われなかった場合はシード値になります。

`M` が 0 以外の場合、テンプレート引数 `A` と `C` の値は `M` 未満である必要があります。

このエンジンから直接ジェネレーターを構築できますが、定義済みの typedef のいずれかを使用することもできます。

`minstd_rand0`: 1988 年の最小標準エンジン (ルイス、グッドマン、ミラー、1969 年)。

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: `minstd_rand0` の改良版最小標準エンジン (パーク、ミラー、ストックマイヤー、1993 年)。

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

線形合同法エンジン アルゴリズムの詳細については、Wikipedia の記事「[Linear congruential generator (線形合同法)](http://go.microsoft.com/fwlink/p/?linkid=402446)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
