---
title: index クラス
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 50222015e6b365dc161fd4334067c26c7f288337
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365159"
---
# <a name="index-class"></a>index クラス

*N*次元インデックス ベクトルを定義します。

## <a name="syntax"></a>構文

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
ランク (次元数)。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[インデックス コンストラクタ](#index_ctor)|`index` クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[演算子 --](#operator--)|`index` オブジェクトの各要素をデクリメントします。|
|[演算子%=](#operator_mod_eq)|その要素がある数で除算された場合、`index` オブジェクトの各要素の剰余を計算します。|
|[演算子*=](#operator_star_eq)|`index` オブジェクトの各要素をある数で乗算します。|
|[演算子/=](#operator_div_eq)|`index` オブジェクトの各要素をある数で除算します。|
|[インデックス::演算子\[\]](#operator_at)|指定したインデックス位置にある要素を返します。|
|[演算子++](#operator_add_add)|`index` オブジェクトの各要素をインクリメントします。|
|[演算子 +=](#operator_add_eq)|指定した数を `index` オブジェクトの各要素に加算します。|
|[演算子=](#operator_eq)|指定された `index` オブジェクトの内容をこのオブジェクトにコピーします。|
|[演算子-=](#operator_-_eq)|指定した数を `index` オブジェクトの各要素から減算します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[ランク定数](#rank)|`index` オブジェクトのランクを格納します。|

## <a name="inheritance-hierarchy"></a>継承階層

`index`

## <a name="remarks"></a>解説

この`index`構造体は *、N*次元空間内の一意の位置を指定する*N*個の整数の座標ベクトルを表します。 ベクターの値は最上位から最下位へ順に並べ替えられます。 [operator=](#operator_eq)を使用して、コンポーネントの値を取得できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** amp.h

**名前空間:** Concurrency

## <a name="index-constructor"></a><a name="index_ctor"></a>インデックス コンストラクタ

index クラスの新しいインスタンスを初期化します。

```cpp
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Array*<br/>
ランク値を持つ 1 次元配列。

*_I*<br/>
1 次元インデックスのインデックス位置。

*_I0*<br/>
最上位の次元の長さ。

*_I1*<br/>
最上位の次の次元の長さ。

*_I2*<br/>
最下位の次元の長さ。

*_Other*<br/>
新しいインデックス オブジェクトの基になるインデックス オブジェクト。

## <a name="operator--"></a><a name="operator--"></a>演算子 --

index オブジェクトの各要素をデクリメントします。

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>戻り値

接頭語演算子の場合、インデックスオブジェクト (*this)。 サフィックス演算子の場合は、新しいインデックス オブジェクト。

## <a name="operator"></a><a name="operator_mod_eq"></a>演算子%=

指定した数値で要素を除算した場合に、インデックス オブジェクト内の各要素の剰余を計算します。

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
係数を見つけるために除算する数値。

## <a name="return-value"></a>戻り値

インデックス オブジェクト。

## <a name="operator"></a><a name="operator_star_eq"></a>演算子*=

index オブジェクトの各要素を指定した数で乗算します。

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
乗算対象の数です。

## <a name="operator"></a><a name="operator_div_eq"></a>演算子/=

指定された数で index オブジェクトの各要素を除算します。

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
除数。

## <a name="operator"></a><a name="operator_at"></a>演算子\[\]

指定した位置にあるインデックスのコンポーネントを返します。

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Index*<br/>
0 からランク - 1 までの整数。

### <a name="return-value"></a>戻り値

指定したインデックス位置にある要素。

### <a name="remarks"></a>解説

次の例では、インデックスのコンポーネント値を表示します。

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator"></a><a name="operator_add_add"></a>演算子++

index オブジェクトの各要素をインクリメントします。

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>戻り値

接頭語演算子の場合、インデックスオブジェクト (*this)。 サフィックス演算子の場合は、新しいインデックス オブジェクト。

## <a name="operator"></a><a name="operator_add_eq"></a>演算子 +=

指定した数を index オブジェクトの各要素に加算します。

```cpp
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
加算する数。

### <a name="return-value"></a>戻り値

インデックス オブジェクト。

## <a name="operator"></a><a name="operator_eq"></a>演算子=

指定された index オブジェクトの内容をこのオブジェクトにコピーします。

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピー元のインデックス オブジェクト。

### <a name="return-value"></a>戻り値

このインデックス オブジェクトへの参照。

## <a name="operator-"></a><a name="operator_-_eq"></a>演算子-=

指定した数を index オブジェクトの各要素から減算します。

```cpp
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
減算する数。

### <a name="return-value"></a>戻り値

インデックス オブジェクト。

## <a name="rank"></a><a name="rank"></a>ランク

インデックス オブジェクトのランクを取得します。

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>関連項目

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
