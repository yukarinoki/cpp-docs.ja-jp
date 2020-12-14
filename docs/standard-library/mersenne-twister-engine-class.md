---
description: '詳細情報: mersenne_twister_engine クラス'
title: mersenne_twister_engine クラス
ms.date: 11/04/2016
f1_keywords:
- random/std::mersenne_twister_engine
helpviewer_keywords:
- mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
ms.openlocfilehash: 7f5a2d74493194cb07bb4dd628cf3e483b1fd99b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230628"
---
# <a name="mersenne_twister_engine-class"></a>mersenne_twister_engine クラス

メルセンヌ ツイスタ アルゴリズムを基にして、品質の高い整数のランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class UIntType,
    size_t W, size_t N, size_t M, size_t R,
    UIntType A, size_t U, UIntType D, size_t S,
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>
class mersenne_twister_engine;
```

### <a name="parameters"></a>パラメーター

*UIntType*\
結果を表す符号なし整数型。 使用できる型については、「」を参照してください [\<random>](../standard-library/random.md) 。

*リダイレクト*\
**ワード サイズ**。 状態シーケンスの各ワードのサイズ (ビット数)。 **前提条件**: `2u < W ≤ numeric_limits<UIntType>::digits`

*非該当*\
**状態のサイズ**。 状態シーケンス内の要素 (値) の数。

*M*\
**シフト サイズ**。 ひねりを加えるごとにスキップする要素の数。 **前提条件**: `0 < M ≤ N`

*\R\n\r\n*\
**マスク ビット**。 **前提条件**: `R ≤ W`

*ある*\
**XOR マスク**。 **前提条件**: `A ≤ (1u<<W) - 1u`

*U*、 *S*、 *T*、 *L*\
**調律のシフト パラメーター**。 スクランブル (調律) 時のシフト値として使用されます。 前提条件: `U,S,T,L ≤ W`

*D*、 *B*、 *C*\
**調律のビット マスク パラメーター**。 スクランブル (調律) 時のビット マスク値として使用されます。 前提条件: `D,B,C ≤ (1u<<W) - 1u`

*F*\
**初期化乗数**。 シーケンスの初期化を支援するために使用されます。 前提条件: `F ≤ (1u<<W) - 1u`

## <a name="members"></a>メンバー

`mersenne_twister_engine::mersenne_twister_engine`\
`mersenne_twister_engine::discard`\
`mersenne_twister_engine::max`\
`mersenne_twister_engine::min`\
`mersenne_twister_engine::operator()`\
`mersenne_twister_engine::seed`

`default_seed` は、`5489u` として定義されているメンバー定数で、`mersenne_twister_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。

エンジンメンバーの詳細については、「」を参照してください [\<random>](../standard-library/random.md) 。

## <a name="remarks"></a>解説

このクラステンプレートは、終了間隔 [, W] で値を返す乱数エンジンを記述し `0` `2` <sup></sup>  -  `1` ます。 このエンジンは、`W * (N - 1) + R` ビットの大きな整数値を保持します。 この大きな値から一度に1ビットずつ抽出し、すべて *のビットを* 使用した場合は、ビットをシフトして混合することによって大きな値をひねることによって、抽出元となる新しいビットのセットを取得します。 エンジンの状態は、 `N` `W` が N 回以上呼び出された場合に使用される最後のビット値です。それ以外の場合は、 `operator()` 使用された `M` `W` ビット値と `N - M` シードの最後の値です。

ジェネレーターは、シフト値 *N* と *M*、ねじれ値 *R*、および条件付き XOR マスク *a* によって定義された、ツイスト一般化されたフィードバックシフトレジスタを使用して、保持している大きな値をひねることができます。さらに、生のシフトレジスタのビットは、 *U*、 *D*、 *S*、 *B*、 *T*、 *C*、 *L* の値によって定義されるビットスクランブル行列に従って、スクランブル (調律) されます。

テンプレート引数は、 `UIntType` 最大 W の値を保持するのに十分な大きさである必要があり `2` <sup></sup>  -  `1` ます。 その他のテンプレート引数の値は、次の要件を満たしている必要があります。`2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`

このエンジンから直接ジェネレーターを構築できますが、次の表にある定義済みの typedef のいずれかを使用することをお勧めします。

`mt19937`: 32 ビット メルセンヌ ツイスタ エンジン (松本、西村、1998年)。

```cpp
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,
    31, 0x9908b0df,
    11, 0xffffffff,
    7, 0x9d2c5680,
    15, 0xefc60000,
    18, 1812433253> mt19937;
```

`mt19937_64`: 64 ビット メルセンヌ ツイスタ エンジン (松本、西村、2000年)。

```cpp
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,
    31, 0xb5026f5aa96619e9ULL,
    29, 0x5555555555555555ULL,
    17, 0x71d67fffeda60000ULL,
    37, 0xfff7eee000000000ULL,
    43, 6364136223846793005ULL> mt19937_64;
```

メルセンヌ ツイスタ アルゴリズムの詳細については、Wikipedia の記事「[メルセンヌ ツイスタ](https://go.microsoft.com/fwlink/p/?linkid=402356)」をご覧ください。

## <a name="example"></a>例

コード例については、「」を参照してください [\<random>](../standard-library/random.md) 。

## <a name="requirements"></a>要件

**ヘッダー:**\<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)
