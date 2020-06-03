---
title: 数値 (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/numeric>
- cliext::accumulate
- cliext::adjacent_difference
- cliext::inner_product
- cliext::partial_sum
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
- accumulate function [STL/CLR]
- adjacent_difference function [STL/CLR]
- inner_product function [STL/CLR]
- partial_sum function [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
ms.openlocfilehash: 1939a6dd9b6d8186eb278623f3b0a5a3d851f4d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208482"
---
# <a name="numeric-stlclr"></a>数値 (STL/CLR)

数値処理のために提供されるアルゴリズムを実行するコンテナーテンプレート関数を定義します。

## <a name="syntax"></a>構文

```
#include <cliext/numeric>
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<cliext/numeric >

**名前空間:** cliext

## <a name="declarations"></a>宣言

|Function|説明|
|--------------|-----------------|
|[accumulate (STL/CLR)](#accumulate)|連続する部分和を計算することで、いくつかの初期値を含め、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を計算します。|
|[adjacent_difference (STL/CLR)](#adjacent_difference)|入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[inner_product (STL/CLR)](#inner_product)|2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[partial_sum (STL/CLR)](#partial_sum)|最初の要素から `i`th 要素までの一連の合計を計算し、その各合計の結果をターゲット範囲の `i`番目の要素に格納します。または、sum 操作が指定した別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|

## <a name="members"></a>メンバー

## <a name="accumulate-stlclr"></a><a name="accumulate"></a>累積 (STL/CLR)

連続する部分和を計算することで、いくつかの初期値を含め、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を計算します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _Ty> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);
template<class _InIt, class _Ty, class _Fn2> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);
```

### <a name="remarks"></a>解説

この関数は、標準ライブラリのC++数値関数 `accumulate`と同じように動作します。 詳細については、「[累積](../standard-library/numeric-functions.md#accumulate)」を参照してください。

## <a name="adjacent_difference-stlclr"></a><a name="adjacent_difference"></a>adjacent_difference (STL/CLR)

入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,
        _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>解説

この関数は、標準ライブラリのC++数値関数 `adjacent_difference`と同じように動作します。 詳細については、「 [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)」を参照してください。

## <a name="inner_product-stlclr"></a><a name="inner_product"></a>inner_product (STL/CLR)

2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2, class _Ty> inline
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Ty _Val);
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,
       class _Fn22> inline
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);
```

### <a name="remarks"></a>解説

この関数は、標準ライブラリのC++数値関数 `inner_product`と同じように動作します。 詳細については、「 [inner_product](../standard-library/numeric-functions.md#inner_product)」を参照してください。

## <a name="partial_sum-stlclr"></a><a name="partial_sum"></a>partial_sum (STL/CLR)

最初の要素から `i`th 要素までの一連の合計を計算し、その各合計の結果をターゲット範囲の `i`番目の要素に格納します。または、sum 操作が指定した別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>解説

この関数は、標準ライブラリのC++数値関数 `partial_sum`と同じように動作します。 詳細については、「 [partial_sum](../standard-library/numeric-functions.md#partial_sum)」を参照してください。
