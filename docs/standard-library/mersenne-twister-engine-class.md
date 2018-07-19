---
title: mersenne_twister_engine クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::mersenne_twister_engine
dev_langs:
- C++
helpviewer_keywords:
- mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb03b35ed792bda7c506fd06d6102dda83c768e6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959272"
---
# <a name="mersennetwisterengine-class"></a>mersenne_twister_engine クラス

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

*UIntType*符号なし整数の結果の型。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。

*W* **ワード サイズ**します。 状態シーケンスの各ワードのサイズ (ビット数)。 **前提条件**: `2u < W ≤ numeric_limits<UIntType>::digits`

*N* **状態のサイズ**します。 状態シーケンス内の要素 (値) の数。

*M* **シフト サイズ**します。 ひねりを加えるごとにスキップする要素の数。 **前提条件**: `0 < M ≤ N`

*R* **マスク ビット**します。 **前提条件**: `R ≤ W`

*A* **XOR マスク**します。 **前提条件**: `A ≤ (1u<<W) - 1u`

*U*、 *S*、 *T*、 *L* **Tempering シフト パラメーター**します。 スクランブル (調律) 時のシフト値として使用されます。 前提条件: `U,S,T,L ≤ W`

*D*、 *B*、 *C* **Tempering ビット マスク パラメーター**します。 スクランブル (調律) 時のビット マスク値として使用されます。 前提条件: `D,B,C ≤ (1u<<W) - 1u`

*F* **初期化乗数**します。 シーケンスの初期化を支援するために使用されます。 前提条件: `F ≤ (1u<<W) - 1u`

## <a name="members"></a>メンバー

||||
|-|-|-|
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|

`default_seed` は、`5489u` として定義されているメンバー定数で、`mersenne_twister_engine::seed` および単一値コンストラクターの既定のパラメーター値として使用されます。

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>Remarks

このテンプレート クラスは、閉区間 [ `0`, `2`<sup>W</sup> - `1`] の値を返す乱数エンジンを表します。 このエンジンは、`W * (N - 1) + R` ビットの大きな整数値を保持します。 抽出*W*この大きな値からを使用して、すべてのビットが使用時のビット シフトをから抽出するビットの新しいセットを持つようにビットを混在して、大きな値をひねること。 エンジンの状態は`N` `W`-ビットの場合は、値`operator()`少なくともが呼び出された*N*タイムアウトと、それ以外の場合、 `M` `W`-ビットが使用されている値と最終`N - M` seed の値。

コード ジェネレーター、シフト値によって定義された汎用ツイストのフィードバック シフト レジスタを使用して、保持している大きな値にひねりを加える*N*と*M*、ひねり値*R*、および条件付きの XOR マスク*A*します。さらに、生のシフト レジスタのビットは、スクランブル (調律) 値で定義されたビット スクランブル用行列に従って*U*、 *D*、 *S*、 *B*、 *T*、 *C*、および*L*します。

テンプレート引数 `UIntType` には、最大 `2`<sup>W</sup> - `1` の値を保持するのに十分な大きさが必要です。 その他のテンプレート引数の値は、次の要件を満たしている必要があります。`2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`

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

メルセンヌ ツイスタ アルゴリズムの詳細については、Wikipedia の記事「[メルセンヌ ツイスタ](http://go.microsoft.com/fwlink/p/?linkid=402356)」をご覧ください。

## <a name="example"></a>例

コード例については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
