---
title: linear_congruential_engine クラス
ms.date: 11/04/2016
f1_keywords:
- random/std::linear_congruential_engine
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
ms.openlocfilehash: 83306e47995f652014682d6bcc94966aab75c062
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413256"
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

*UIntType*<br/>
結果を表す符号なし整数型。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。

*A*<br/>
**乗数**します。 **Precondition**:「解説」セクションをご覧ください。

*C*<br/>
**インクリメント**します。 **Precondition**:「解説」セクションをご覧ください。

*M*<br/>
**剰余**します。 **Precondition**:「解説」を参照してください。

## <a name="members"></a>メンバー

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed` は、`1u` として定義されているメンバー定数で、`linear_congruential_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>Remarks

`linear_congruential_engine` テンプレート クラスは、最も単純なジェネレーター エンジンですが、速度や品質は最高というわけではありません。 このエンジンを改良したものが [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md) です。 これらのエンジンはいずれも、[mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md) ほど高速ではなく、結果も高品質ではありません。

このエンジンは、漸化式 ( *周期*) `x(i) = (A * x(i-1) + C) mod M` を使用して、ユーザー指定の符号なし整数型の値を生成します。

場合*M* 0 の場合は、この剰余演算に使用される値は`numeric_limits<result_type>::max() + 1`します。 エンジンの状態は、最後に返された値か、または `operator()` に対して呼び出しが行われなかった場合はシード値になります。

場合*M* 、テンプレート引数の値に 0 以外は*A*と*C*必要がありますより小さい*M*します。

このエンジンから直接ジェネレーターを構築できますが、定義済みの typedef のいずれかを使用することもできます。

`minstd_rand0`:1988 年の最小標準エンジン (ルイス、グッドマン、ミラー、1969 年)。

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`:`minstd_rand0` の改良版最小標準エンジン (パーク、ミラー、ストックマイヤー、1993 年)。

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

線形合同法エンジン アルゴリズムの詳細については、Wikipedia の記事「[Linear congruential generator (線形合同法)](http://go.microsoft.com/fwlink/p/?linkid=402446)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
