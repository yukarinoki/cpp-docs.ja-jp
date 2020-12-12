---
description: '詳細情報: アルゴリズム (STL/CLR)'
title: algorithm (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/algorithm>
- cliext::adjacent_find
- cliext::binary_search
- cliext::copy
- cliext::copy_backward
- cliext::count
- cliext::count_if
- cliext::equal
- cliext::equal_range
- cliext::fill
- cliext::fill_n
- cliext::find
- cliext::find_end
- cliext::find_first_of
- cliext::find_if
- cliext::for_each
- cliext::generate
- cliext::generate_n
- cliext::includes
- cliext::inplace_merge
- cliext::iter_swap
- cliext::lexicographical_compare
- cliext::lower_bound
- cliext::make_heap
- cliext::max
- cliext::max_element
- cliext::merge
- cliext::min
- cliext::min_element
- cliext::mismatch
- cliext::next_permutation
- cliext::nth_element
- cliext::partial_sort
- cliext::partial_sort_copy
- cliext::partition
- cliext::pop_heap
- cliext::prev_permutation
- cliext::push_heap
- cliext::random_shuffle
- cliext::remove
- cliext::remove_copy
- cliext::remove_copy_if
- cliext::remove_if
- cliext::replace
- cliext::replace_copy
- cliext::replace_copy_if
- cliext::replace_if
- cliext::reverse
- cliext::reverse_copy
- cliext::rotate
- cliext::rotate_copy
- cliext::search
- cliext::search_n
- cliext::set_difference
- cliext::set_intersection
- cliext::set_symmetric_difference
- cliext::set_union
- cliext::sort
- cliext::sort_heap
- cliext::stable_partition
- cliext::stable_sort
- cliext::swap
- cliext::swap_ranges
- cliext::transform
- cliext::unique
- cliext::unique_copy
- cliext::upper_bound
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
- adjacent_find function
- binary_search function [STL/CLR]
- copy function [STL/CLR]
- copy_backward function [STL/CLR]
- count function [STL/CLR]
- count_if function [STL/CLR]
- equal function [STL/CLR]
- equal_range function [STL/CLR]
- fill function
- fill_n function
- find function [STL/CLR]
- find_end function [STL/CLR]
- find_first_of function [STL/CLR]
- find_if function [STL/CLR]
- for_each function [STL/CLR]
- generate function [STL/CLR]
- generate_n function [STL/CLR]
- includes function [STL/CLR]
- inplace_merge function [STL/CLR]
- iter_swap function [STL/CLR]
- lexicographical_compare function [STL/CLR]
- lower_bound function [STL/CLR]
- make_heap function [STL/CLR]
- max function [STL/CLR]
- max_element function [STL/CLR]
- merge function [STL/CLR]
- min function [STL/CLR]
- min_element function [STL/CLR]
- mismatch function [STL/CLR]
- next_permutation function [STL/CLR]
- nth_element function [STL/CLR]
- partial_sort function [STL/CLR]
- partial_sort_copy function [STL/CLR]
- partition function [STL/CLR]
- pop_heap function [STL/CLR]
- prev_permutation function [STL/CLR]
- push_heap function [STL/CLR]
- random_shuffle function [STL/CLR]
- remove function [STL/CLR]
- remove_copy function [STL/CLR]
- remove_copy_if function [STL/CLR]
- remove_if function [STL/CLR]
- replace function [STL/CLR]
- replace_copy function [STL/CLR]
- replace_copy_if function [STL/CLR]
- replace_if function [STL/CLR]
- reverse function [STL/CLR]
- reverse_copy function [STL/CLR]
- rotate function [STL/CLR]
- rotate_copy function [STL/CLR]
- search function [STL/CLR]
- search_n function [STL/CLR]
- set_difference function [STL/CLR]
- set_intersection function [STL/CLR]
- set_symmetric_difference function [STL/CLR]
- set_union function [STL/CLR]
- sort function [STL/CLR]
- sort_heap function [STL/CLR]
- stable_partition function [STL/CLR]
- stable_sort function [STL/CLR]
- swap function [STL/CLR]
- swap_ranges function [STL/CLR]
- transform function [STL/CLR]
- unique function [STL/CLR]
- unique_copy function [STL/CLR]
- upper_bound function [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
ms.openlocfilehash: 450a4afdf5c5d697d722e92132c5c59e74064f5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282836"
---
# <a name="algorithm-stlclr"></a>algorithm (STL/CLR)

アルゴリズムを実行する STL/CLR コンテナーテンプレート関数を定義します。

## <a name="syntax"></a>構文

```cpp
#include <cliext/algorithm>
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cliext/algorithm>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|機能|説明|
|--------------|-----------------|
|[adjacent_find (STL/CLR)](#adjacent_find)|等しい2つの隣接する要素を検索します。|
|[binary_search (STL/CLR)](#binary_search)|並べ替えられたシーケンスに特定の値が含まれているかどうかをテストします。|
|[copy (STL/CLR)](#copy)|ソース範囲からターゲット範囲に値をコピーし、前方方向に反復処理します。|
|[copy_backward (STL/CLR)](#copy_backward)|ソース範囲からターゲット範囲に値をコピーします。逆方向に反復処理を行います。|
|[count (STL/CLR)](#count)|範囲内で値が指定された値と一致する要素の数を返します。|
|[count_if (STL/CLR)](#count_if)|範囲内で値が指定された条件と一致する要素の数を返します。|
|[equal (STL/CLR)](#equal)|2つの範囲を要素ごとに比較します。|
|[equal_range (STL/CLR)](#equal_range)|順序付けられた一連の値を検索し、指定した要素と等しい値のサブシーケンスを区切る2つの位置を返します。|
|[fill (STL/CLR)](#fill)|指定された範囲のすべての要素に同じ新しい値を割り当てます。|
|[fill_n (STL/CLR)](#fill_n)|特定の要素で始まる要素範囲で、指定された数の要素に新しい値を割り当てます。|
|[find (STL/CLR)](#find)|指定された値が最初に出現する位置を返します。|
|[find_end (STL/CLR)](#find_end)|指定したシーケンスと同じ範囲内の最後のサブシーケンスを返します。|
|[find_first_of (STL/CLR)](#find_first_of)|範囲内で、指定された要素の範囲のうち最初に出現するものを検索します。|
|[find_if (STL/CLR)](#find_if)|要素が指定された条件を満たす場合に、値のシーケンス内の最初の要素の位置を返します。|
|[for_each (STL/CLR)](#for_each)|指定された関数オブジェクトを値のシーケンスの各要素に適用し、関数オブジェクトを返します。|
|[generate (STL/CLR)](#generate)|関数オブジェクトによって生成された値を、値のシーケンスの各要素に割り当てます。|
|[generate_n (STL/CLR)](#generate_n)|関数オブジェクトによって生成された値を、指定した数の要素に割り当てます。|
|[includes (STL/CLR)](#includes)|1つの並べ替えられた範囲に2番目の並べ替えられた範囲のすべての要素が含まれるかどうかをテストします|
|[inplace_merge (STL/CLR)](#inplace_merge)|2つの連続する並べ替えられた範囲の要素を、単一の並べ替えられた範囲に結合します。|
|[iter_swap (STL/CLR)](#iter_swap)|指定された反復子のペアで参照される 2 個の値を交換します。|
|[lexicographical_compare (STL/CLR)](#lexicographical_compare)|2つのシーケンスを要素ごとに比較して、2つのシーケンスのうち小さい方のシーケンスを識別します。|
|[lower_bound (STL/CLR)](#lower_bound)|指定した値以上の値を持つ、順序付けられた一連の値の最初の要素の位置を検索します。|
|[make_heap (STL/CLR)](#make_heap)|指定された範囲の要素を、ヒープの最初の要素が最大のヒープに変換します。|
|[max (STL/CLR)](#max))|2つのオブジェクトを比較し、2つのオブジェクトのうち大きい方を返します。|
|[max_element (STL/CLR)](#max_element)|指定した値のシーケンス内の最大の要素を検索します。|
|[merge (STL/CLR)](#merge))|2つの並べ替えられたソース範囲のすべての要素を、単一の並べ替えられたターゲット範囲に結合します。|
|[min (STL/CLR)](#min)|2つのオブジェクトを比較し、そのうち小さい方のオブジェクトを返します。|
|[min_element (STL/CLR)](#min_element)|指定した値のシーケンス内の最小の要素を検索します。|
|[mismatch (STL/CLR)](#mismatch)|2つの範囲を要素ごとに比較し、差が発生した最初の位置を返します。|
|[next_permutation (STL/CLR)](#next_permutation)|範囲内の要素を並べ替えることにより、元の順序が、辞書式が存在する場合は、次に大きい順列に置換されるようにします。|
|[nth_element (STL/CLR)](#nth_element)|要素のシーケンスをパーティション分割します。シーケンスの最初の要素の前にあるすべての要素がその値以下であり、その後に続くすべての要素がそれ以上で `n` あることを確認します。|
|[partial_sort (STL/CLR)](#partial_sort)|範囲内の指定した数の小さい要素を、降順以外の順序に配置します。|
|[partial_sort_copy (STL/CLR)](#partial_sort_copy)|ソース範囲からターゲット範囲に要素をコピーして、ソース範囲の要素が順序付けされるようにします。|
|[partition (STL/CLR)](#partition)|単項述語を満たす要素が、それを満たさない要素よりも前にあるように、範囲内の要素を配置します。|
|[pop_heap (STL/CLR)](#pop_heap)|最大の要素をヒープの先頭から末尾に移動し、残りの要素から新しいヒープを形成します。|
|[prev_permutation (STL/CLR)](#prev_permutation)|要素のシーケンスを並べ替えることによって、元の順序が存在する場合は、辞書式の前に大きい順列を置き換えます。|
|[push_heap (STL/CLR)](#push_heap)|範囲の末尾にある要素を、範囲内の以前の要素で構成される既存のヒープに追加します。|
|[random_shuffle (STL/CLR)](#random_shuffle)|範囲内の要素のシーケンスを `N` のいずれかに再配置し `N` ます。 個の可能な配置の 1 つに再配置します。|
|[remove (STL/CLR)](#remove)|残りの要素の順序には関係なく、指定された範囲から指定された値を削除し、指定された値を含まない新しい範囲の末尾を返します。|
|[remove_copy (STL/CLR)](#remove_copy)|ソース範囲からターゲット範囲に要素をコピーします。ただし、指定した値の要素は、残りの要素の順序を損なうことなくコピーされません。|
|[remove_copy_if (STL/CLR)](#remove_copy_if)|ソース範囲からターゲット範囲に要素をコピーします。ただし、述語を満たすものは、残りの要素の順序には適合しません。|
|[remove_if (STL/CLR)](#remove_if)|残りの要素の順序を損なうことなく、指定された範囲から述語を満たす要素を削除します。 .|
|[replace (STL/CLR)](#replace)|指定した値と一致する範囲の要素を新しい値に置き換えます。|
|[replace_copy (STL/CLR)](#replace_copy)|ソース範囲からターゲット範囲に要素をコピーし、指定した値と一致する要素を新しい値に置き換えます。|
|[replace_copy_if (STL/CLR)](#replace_copy_if)|ソース範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えて結果を新しいターゲット範囲にコピーします。|
|[replace_if (STL/CLR)](#replace_if)|範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えます。|
|[reverse (STL/CLR)](#reverse)|範囲内の要素の順序を反転させます。|
|[reverse_copy (STL/CLR)](#reverse_copy)|ソース範囲内の要素の順序を反転し、ターゲット範囲にコピーします。|
|[rotate (STL/CLR)](#rotate)|2 つの隣接する範囲の要素を交換します。|
|[rotate_copy (STL/CLR)](#rotate_copy)|ソース範囲内の 2 つの隣接する範囲の要素を交換し、結果をターゲット範囲にコピーします。|
|[search (STL/CLR)](#search_)|要素が特定の要素シーケンス内の要素と等しいか、または要素が二項述語で指定される意味において特定のシーケンス内の要素と等価であるシーケンスが、対象範囲内で最初に出現する位置を検索します。|
|[search_n (STL/CLR)](#search_n)|特定の値を持つか、二項述語によって指定される値と関連する、指定された数の要素で構成される範囲内の最初のサブシーケンスを検索します。|
|[set_difference (STL/CLR)](#set_difference)|1 つの並べ替えられたソース範囲内に属するが、2 番目の並べ替えられたソース範囲には属さないすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|
|[set_intersection (STL/CLR)](#set_intersection)|両方の並べ替えられたソース範囲に属するすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|
|[set_symmetric_difference (STL/CLR)](#set_symmetric_difference)|並べ替えられたソース範囲の一方には属するが、両方には属さないすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|
|[set_union (STL/CLR)](#set_union))|2 つの並べ替えられたソース範囲の少なくとも一方に属するすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|
|[sort (STL/CLR)](#sort)|指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って配置します。|
|[sort_heap (STL/CLR)](#sort_heap)|ヒープを並べ替えられた範囲に変換します。|
|[stable_partition (STL/CLR)](#stable_partition)|範囲内の要素を 2 つの分離されたセットに分類し、等価要素の相対順序は維持して、単項述語を満たす要素が単項述語を満たさない要素よりも前に来るように配置します。|
|[stable_sort (STL/CLR)](#stable_sort)|指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、等価要素の相対順序を維持して配置します。|
|[swap (STL/CLR)](#swap)|2 種類のオブジェクトの間で、最初のオブジェクトの内容を 2 番目のオブジェクトに割り当て、2 番目のオブジェクトの内容を最初のオブジェクトに割り当てて、要素の値を交換します。|
|[swap_ranges (STL/CLR)](#swap_ranges)|1 つの範囲の要素を、同じサイズの別の範囲の要素と交換します。|
|[transform (STL/CLR)](#transform)|指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をターゲット範囲にコピーします。|
|[unique (STL/CLR)](#unique)|指定された範囲内の互いに隣接する重複要素を削除します。|
|[unique_copy (STL/CLR)](#unique_copy)|互いに隣接する重複要素を除き、ソース範囲の要素をターゲット範囲にコピーします。|
|[upper_bound (STL/CLR)](#upper_bound)|順序の基準が二項述語で指定できる場合に、順序付けられた範囲内で、指定した値を超える値を持つ最初の要素の位置を検索します。|

## <a name="members"></a>メンバー

## <a name="adjacent_find-stlclr"></a><a name="adjacent_find"></a> adjacent_find (STL/CLR)

等しいか、または指定された条件を満たす 2 個の隣接する要素を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt> inline
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `adjacent_find` ます。 詳細については、「 [adjacent_find](../standard-library/algorithm-functions.md#adjacent_find)」を参照してください。

## <a name="binary_search-stlclr"></a><a name="binary_search"></a> binary_search (STL/CLR)

並べ替えられた範囲に、指定された値と等しい要素が存在するか、または二項述語で指定された意味で、指定された値と等価の要素が存在するかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    bool binary_search(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    bool binary_search(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `binary_search` ます。 詳細については、「 [binary_search](../standard-library/algorithm-functions.md#binary_search)」を参照してください。

## <a name="copy-stlclr"></a><a name="copy"></a> コピー (STL/CLR)

要素のソース シーケンス全体を繰り返し、順方向の新しい位置を割り当てて、ソース範囲内からターゲットの範囲に要素の値を割り当てます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `copy` ます。 詳細については、「 [copy](../standard-library/algorithm-functions.md#copy)」を参照してください。

## <a name="copy_backward-stlclr"></a><a name="copy_backward"></a> copy_backward (STL/CLR)

要素のソース シーケンス全体を繰り返し、逆方向の新しい位置を割り当てて、ソース範囲内からターゲットの範囲に要素の値を割り当てます。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt1, class _BidIt2> inline
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,
        _BidIt2 _Dest);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `copy_backward` ます。 詳細については、「 [copy_backward](../standard-library/algorithm-functions.md#copy_backward)」を参照してください。

## <a name="count-stlclr"></a><a name="count"></a> カウント (STL/CLR)

範囲内で値が指定された値と一致する要素の数を返します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _Ty> inline
    typename iterator_traits<_InIt>::difference_type
        count(_InIt _First, _InIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `count` ます。 詳細については、「 [count](../standard-library/algorithm-functions.md#count)」を参照してください。

## <a name="count_if-stlclr"></a><a name="count_if"></a> count_if (STL/CLR)

範囲内で値が指定された条件と一致する要素の数を返します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _Pr> inline
    typename iterator_traits<_InIt>::difference_type
        count_if(_InIt _First, _InIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `count_if` ます。 詳細については、「 [count_if](../standard-library/algorithm-functions.md#count_if)」を参照してください。

## <a name="equal-stlclr"></a><a name="equal"></a> 等しい (STL/CLR)

二項述語によって指定された等値または等価について、2 つの範囲を要素ごとに比較します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2> inline
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);
template<class _InIt1, class _InIt2, class _Pr> inline
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `equal` ます。 詳細については、「 [equal](../standard-library/algorithm-functions.md#equal)」を参照してください。

## <a name="equal_range-stlclr"></a><a name="equal_range"></a> equal_range (STL/CLR)

順序付けられた範囲内で、最初の位置が指定された要素の位置以下で、2 番目の位置が要素の位置を超える位置のペアを検索します。ここで、シーケンス内の位置を確立するために使用される等価または順序付けの意味は、二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `equal_range` ます。 詳細については、「 [equal_range](../standard-library/algorithm-functions.md#equal_range)」を参照してください。

## <a name="fill-stlclr"></a><a name="fill"></a> fill (STL/CLR)

指定された範囲のすべての要素に同じ新しい値を割り当てます。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `fill` ます。 詳細については、「 [fill](../standard-library/algorithm-functions.md#fill)」を参照してください。

## <a name="fill_n-stlclr"></a><a name="fill_n"></a> fill_n (STL/CLR)

特定の要素で始まる要素範囲で、指定された数の要素に新しい値を割り当てます。

### <a name="syntax"></a>構文

```cpp
template<class _OutIt, class _Diff, class _Ty> inline
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `fill_n` ます。 詳細については、「 [fill_n](../standard-library/algorithm-functions.md#fill_n)」を参照してください。

## <a name="find-stlclr"></a><a name="find"></a> find (STL/CLR)

範囲内で指定された値を持つ要素が最初に出現する位置を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _Ty> inline
    _InIt find(_InIt _First, _InIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `find` ます。 詳細については、「 [find](../standard-library/algorithm-functions.md#find)」を参照してください。

## <a name="find_end-stlclr"></a><a name="find_end"></a> find_end (STL/CLR)

範囲内で指定されたシーケンスと等しい、つまり二項述語で指定された意味で等価である最後のサブシーケンスを検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2);
template<class _FwdIt1, class _FwdIt2, class _Pr> inline
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `find_end` ます。 詳細については、「 [find_end](../standard-library/algorithm-functions.md#find_end)」を参照してください。

## <a name="find_first_of-stlclr"></a><a name="find_first_of"></a> find_first_of (STL/CLR)

対象範囲内で複数の値のうち最初に出現するもの、つまり二項述語で指定された意味で、指定された要素のセットと等価である複数の要素のうち最初に出現するものを検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2);
template<class _FwdIt1, class _FwdIt2, class _Pr> inline
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `find_first_of` ます。 詳細については、「 [find_first_of](../standard-library/algorithm-functions.md#find_first_of)」を参照してください。

## <a name="find_if-stlclr"></a><a name="find_if"></a> find_if (STL/CLR)

範囲内で指定された条件を満たす要素が最初に出現する位置を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _Pr> inline
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `find_if` ます。 詳細については、「 [find_if](../standard-library/algorithm-functions.md#find_if)」を参照してください。

## <a name="for_each-stlclr"></a><a name="for_each"></a> for_each (STL/CLR)

範囲内で順方向順序で各要素に対して指定された関数を適用し、関数オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _Fn1> inline
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `for_each` ます。 詳細については、「 [for_each](../standard-library/algorithm-functions.md#for_each)」を参照してください。

## <a name="generate-stlclr"></a><a name="generate"></a> generate (STL/CLR)

範囲内の各要素に関数オブジェクトによって生成される値を割り当てます。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Fn0> inline
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `generate` ます。 詳細については、「 [generate](../standard-library/algorithm-functions.md#generate)」を参照してください。

## <a name="generate_n-stlclr"></a><a name="generate_n"></a> generate_n (STL/CLR)

範囲内の指定された数の要素に関数オブジェクトによって生成される値を割り当て、最後に割り当てられた値を 1 つ超えた位置を返します。

### <a name="syntax"></a>構文

```cpp
template<class _OutIt, class _Diff, class _Fn0> inline
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `generate_n` ます。 詳細については、「 [generate_n](../standard-library/algorithm-functions.md#generate_n)」を参照してください。

## <a name="includes-stlclr"></a><a name="includes"></a> インクルード (STL/CLR)

1 つの並べ替えられた範囲に、別の並べ替えられた範囲内のすべての要素が含まれるかどうかをテストします。要素間の順序または等価の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2> inline
    bool includes(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2);
template<class _InIt1, class _InIt2, class _Pr> inline
    bool includes(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `includes` ます。 詳細については、「 [インクルード](../standard-library/algorithm-functions.md#includes)」を参照してください。

## <a name="inplace_merge-stlclr"></a><a name="inplace_merge"></a> inplace_merge (STL/CLR)

2 つの連続する並べ替えられた範囲の要素を単一の並べ替えられた範囲として連結します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt> inline
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,
        _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `inplace_merge` ます。詳細については、「 [inplace_merge](../standard-library/algorithm-functions.md#inplace_merge)」を参照してください。

## <a name="iter_swap-stlclr"></a><a name="iter_swap"></a> iter_swap (STL/CLR)

指定された反復子のペアで参照される 2 個の値を交換します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    void iter_swap(_FwdIt1 _Left, _FwdIt2 _Right);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `iter_swap` ます。 詳細については、「 [iter_swap](../standard-library/algorithm-functions.md#iter_swap)」を参照してください。

## <a name="lexicographical_compare-stlclr"></a><a name="lexicographical_compare"></a> lexicographical_compare (STL/CLR)

2 つのシーケンスを要素ごとに比較して、2 つのうちどちらが小さいかを判断します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2> inline
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2);
template<class _InIt1, class _InIt2, class _Pr> inline
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `lexicographical_compare` ます。 詳細については、「 [lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare)」を参照してください。

## <a name="lower_bound-stlclr"></a><a name="lower_bound"></a> lower_bound (STL/CLR)

順序の基準が二項述語で指定できる場合に、順序付けられた範囲内で、指定した値以下の値を持つ最初の要素の位置を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `lower_bound` ます。 詳細については、「 [lower_bound](../standard-library/algorithm-functions.md#lower_bound)」を参照してください。

## <a name="make_heap-stlclr"></a><a name="make_heap"></a> make_heap (STL/CLR)

指定された範囲の要素を、最初の要素が最大であるヒープに変換します。並べ替えの基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void make_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `make_heap` ます。 詳細については、「 [make_heap](../standard-library/algorithm-functions.md#make_heap)」を参照してください。

## <a name="max-stlclr"></a><a name="max"></a> max (STL/CLR)

2 つのオブジェクトを比較し、大きい方のオブジェクトを返します。順序の基準は、二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _Ty> inline
    const _Ty max(const _Ty% _Left, const _Ty% _Right);
template<class _Ty, class _Pr> inline
    const _Ty max(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `max` ます。 詳細については、「 [max](../standard-library/algorithm-functions.md#max)」を参照してください。

## <a name="max_element-stlclr"></a><a name="max_element"></a> max_element (STL/CLR)

並べ替え基準をバイナリ述語で指定できる、指定された範囲内の最大の要素の最初の出現箇所を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt> inline
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `max_element` ます。 詳細については、「 [max_element](../standard-library/algorithm-functions.md#max_element)」を参照してください。

## <a name="merge-stlclr"></a><a name="merge"></a> merge (STL/CLR)

2 つの並べ替えられたソース範囲のすべての要素を単一の並べ替えられたターゲット範囲として連結します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `merge` ます。 詳細については、「 [merge](../standard-library/algorithm-functions.md#merge)」を参照してください。

## <a name="min-stlclr"></a><a name="min"></a> min (STL/CLR)

2 つのオブジェクトを比較し、小さい方のオブジェクトを返します。順序の基準は、二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _Ty> inline
    const _Ty min(const _Ty% _Left, const _Ty% _Right);
template<class _Ty, class _Pr> inline
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `min` ます。 詳細については、「 [min](../standard-library/algorithm-functions.md#min)」を参照してください。

## <a name="min_element-stlclr"></a><a name="min_element"></a> min_element (STL/CLR)

指定された範囲内の最小の要素の最初の出現箇所を検索します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt> inline
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `min_element` ます。 詳細については、「 [min_element](../standard-library/algorithm-functions.md#min_element)」を参照してください。

## <a name="mismatch-stlclr"></a><a name="mismatch"></a> 不一致 (STL/CLR)

二項述語によって指定された等値または等価について、2 つの範囲を要素ごとに比較し、相違点が発生する最初の位置を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2> inline
    _PAIR_TYPE(_InIt1)
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);
template<class _InIt1, class _InIt2, class _Pr> inline
    _PAIR_TYPE(_InIt1)
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
            _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `mismatch` ます。 詳細については、「 [不一致](../standard-library/algorithm-functions.md#mismatch)」を参照してください。

## <a name="next_permutation-stlclr"></a><a name="next_permutation"></a> next_permutation (STL/CLR)

範囲内の要素の順序を変更し、元の順序を辞書式に次に大きい順列 (存在する場合) に置き換えます。next の意味は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt> inline
    bool next_permutation(_BidIt _First, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `next_permutation` ます。 詳細については、「 [next_permutation](../standard-library/algorithm-functions.md#next_permutation)」を参照してください。

## <a name="nth_element-stlclr"></a><a name="nth_element"></a> nth_element (STL/CLR)

要素の範囲を分割し、その範囲 `n` 内のシーケンスの th 要素を正しく検索します。これにより、その前にあるすべての要素がそれ以下で、シーケンス内の後続のすべての要素がその値以上になります。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,
        _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `nth_element` ます。 詳細については、「 [nth_element](../standard-library/algorithm-functions.md#nth_element)」を参照してください。

## <a name="partial_sort-stlclr"></a><a name="partial_sort"></a> partial_sort (STL/CLR)

範囲内で指定された数の、より小さい要素を、降順以外の順序、または二項述語で指定された順序の基準に従って配置します。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last,
        _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `partial_sort` ます。 詳細については、「 [partial_sort](../standard-library/algorithm-functions.md#partial_sort)」を参照してください。

## <a name="partial_sort_copy-stlclr"></a><a name="partial_sort_copy"></a> partial_sort_copy (STL/CLR)

ソース範囲からターゲット範囲に要素をコピーします。ソース要素は小なりまたは指定された別の二項述語によって並べ替えられます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _RanIt> inline
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,
        _RanIt _First2, _RanIt _Last2);
template<class _InIt, class _RanIt, class _Pr> inline
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `partial_sort_copy` ます。 詳細については、「 [partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy)」を参照してください。

## <a name="partition-stlclr"></a><a name="partition"></a> パーティション (STL/CLR)

範囲内の要素を 2 つの分離されたセットに分類し、単項述語を満たす要素が単項述語を満たさない要素よりも前に来るように配置します。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt, class _Pr> inline
    _BidIt partition(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `partition` ます。 詳細については、「 [partition](../standard-library/algorithm-functions.md#partition)」を参照してください。

## <a name="pop_heap-stlclr"></a><a name="pop_heap"></a> pop_heap (STL/CLR)

ヒープの先頭と範囲内の最後から 2 番目の位置との間で最大の要素を削除し、残りの要素から新しいヒープを形成します。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void pop_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `pop_heap` ます。 詳細については、「 [pop_heap](../standard-library/algorithm-functions.md#pop_heap)」を参照してください。

## <a name="prev_permutation-stlclr"></a><a name="prev_permutation"></a> prev_permutation (STL/CLR)

範囲内の要素の順序を変更し、元の順序を辞書式に次に大きい順列 (存在する場合) に置き換えます。next の意味は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt> inline
    bool prev_permutation(_BidIt _First, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `prev_permutation` ます。 詳細については、「 [prev_permutation](../standard-library/algorithm-functions.md#prev_permutation)」を参照してください。

## <a name="push_heap-stlclr"></a><a name="push_heap"></a> push_heap (STL/CLR)

範囲の末尾にある要素を、範囲内の以前の要素で構成される既存のヒープに追加します。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void push_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `push_heap` ます。 詳細については、「 [push_heap](../standard-library/algorithm-functions.md#push_heap)」を参照してください。

## <a name="random_shuffle-stlclr"></a><a name="random_shuffle"></a> random_shuffle (STL/CLR)

範囲内の要素のシーケンスを `N` のいずれかに再配置し `N` ます。 個の可能な配置の 1 つに再配置します。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void random_shuffle(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Fn1> inline
    void random_shuffle(_RanIt _First, _RanIt _Last, _Fn1% _Func);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `random_shuffle` ます。 詳細については、「 [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle)」を参照してください。

## <a name="remove-stlclr"></a><a name="remove"></a> remove (STL/CLR)

特定の範囲から指定された値を除去します。残りの要素の順序に影響を及ぼすことはなく、指定された値を含まない新しい範囲の末尾を返します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    _FwdIt remove(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `remove` ます。 詳細については、「 [remove](../standard-library/algorithm-functions.md#remove)」を参照してください。

## <a name="remove_copy-stlclr"></a><a name="remove_copy"></a> remove_copy (STL/CLR)

ソース範囲からターゲット範囲に要素をコピーしますが、指定された値の要素はコピーされません。残りの要素の順序に影響を及ぼすことはなく、新しいターゲット範囲の末尾を返します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt, class _Ty> inline
    _OutIt remove_copy(_InIt _First, _InIt _Last,
        _OutIt _Dest, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `remove_copy` ます。 詳細については、「 [remove_copy](../standard-library/algorithm-functions.md#remove_copy)」を参照してください。

## <a name="remove_copy_if-stlclr"></a><a name="remove_copy_if"></a> remove_copy_if (STL/CLR)

ソース範囲からターゲット範囲に要素をコピーしますが、述語を満たす要素はコピーされません。残りの要素の順序に影響を及ぼすことはなく、新しいターゲット範囲の末尾を返します。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt, class _Pr> inline
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `remove_copy_if` ます。 詳細については、「 [remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if)」を参照してください。

## <a name="remove_if-stlclr"></a><a name="remove_if"></a> remove_if (STL/CLR)

特定の範囲から述語を満たす要素を除去します。残りの要素の順序に影響を及ぼすことはなく、指定された値を含まない新しい範囲の末尾を返します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Pr> inline
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `remove_if` ます。 詳細については、「 [remove_if](../standard-library/algorithm-functions.md#remove_if)」を参照してください。

## <a name="replace-stlclr"></a><a name="replace"></a> replace (STL/CLR)

範囲内の各要素が指定された値に一致するかどうかを調べ、一致する場合は置き換えます。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    void replace(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Oldval, const _Ty% _Newval);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `replace` ます。 詳細については、「 [replace](../standard-library/algorithm-functions.md#replace)」を参照してください。

## <a name="replace_copy-stlclr"></a><a name="replace_copy"></a> replace_copy (STL/CLR)

ソース範囲内の各要素が指定された値に一致するかどうかを調べ、一致する場合は置き換えて結果を新しいターゲット範囲にコピーします。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt, class _Ty> inline
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,
        const _Ty% _Oldval, const _Ty% _Newval);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `replace_copy` ます。 詳細については、「 [replace_copy](../standard-library/algorithm-functions.md#replace_copy)」を参照してください。

## <a name="replace_copy_if-stlclr"></a><a name="replace_copy_if"></a> replace_copy_if (STL/CLR)

ソース範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えて結果を新しいターゲット範囲にコピーします。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Pr _Pred, const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `replace_copy_if` ます。 詳細については、「 [replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if)」を参照してください。

## <a name="replace_if-stlclr"></a><a name="replace_if"></a> replace_if (STL/CLR)

範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えます。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Pr, class _Ty> inline
    void replace_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred,
        const _Ty% _Val);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `replace_if` ます。 詳細については、「 [replace_if](../standard-library/algorithm-functions.md#replace_if)」を参照してください。

## <a name="reverse-stlclr"></a><a name="reverse"></a> reverse (STL/CLR)

範囲内の要素の順序を反転させます。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt> inline
    void reverse(_BidIt _First, _BidIt _Last);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `reverse` ます。 詳細については、「 [reverse](../standard-library/algorithm-functions.md#reverse)」を参照してください。

## <a name="reverse_copy-stlclr"></a><a name="reverse_copy"></a> reverse_copy (STL/CLR)

ソース範囲内の要素の順序を反転し、ターゲット範囲にコピーします。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt, class _OutIt> inline
    _OutIt reverse_copy(_BidIt _First, _BidIt _Last, _OutIt _Dest);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `reverse_copy` ます。 詳細については、「 [reverse_copy](../standard-library/algorithm-functions.md#reverse_copy)」を参照してください。

## <a name="rotate-stlclr"></a><a name="rotate"></a> 回転 (STL/CLR)

2 つの隣接する範囲の要素を交換します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt> inline
    void rotate(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `rotate` ます。 詳細については、「 [回転](../standard-library/algorithm-functions.md#rotate)」を参照してください。

## <a name="rotate_copy-stlclr"></a><a name="rotate_copy"></a> rotate_copy (STL/CLR)

ソース範囲内の 2 つの隣接する範囲の要素を交換し、結果をターゲット範囲にコピーします。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _OutIt> inline
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,
        _OutIt _Dest);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `rotate_copy` ます。 詳細については、「 [rotate_copy](../standard-library/algorithm-functions.md#rotate_copy)」を参照してください。

## <a name="search-stlclr"></a><a name="search_"></a> 検索 (STL/CLR)

要素が特定の要素シーケンス内の要素と等しいか、または要素が二項述語で指定される意味において特定のシーケンス内の要素と等価であるシーケンスが、対象範囲内で最初に出現する位置を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2);
template<class _FwdIt1, class _FwdIt2, class _Pr> inline
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `search` ます。 詳細については、「 [検索](../standard-library/algorithm-functions.md#search)」を参照してください。

## <a name="search_n-stlclr"></a><a name="search_n"></a> search_n (STL/CLR)

特定の値を持つか、二項述語によって指定される値と関連する、指定された数の要素で構成される範囲内の最初のサブシーケンスを検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt1, class _Diff2, class _Ty> inline
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,
        _Diff2 _Count, const _Ty& _Val);
template<class _FwdIt1, class _Diff2, class _Ty, class _Pr> inline
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,
        _Diff2 _Count, const _Ty& _Val, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `search_n` ます。 詳細については、「 [search_n](../standard-library/algorithm-functions.md#search_n)」を参照してください。

## <a name="set_difference-stlclr"></a><a name="set_difference"></a> set_difference (STL/CLR)

1 つの並べ替えられたソース範囲内に属するが、2 番目の並べ替えられたソース範囲には属さないすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `set_difference` ます。 詳細については、「 [set_difference](../standard-library/algorithm-functions.md#set_difference)」を参照してください。

## <a name="set_intersection-stlclr"></a><a name="set_intersection"></a> set_intersection (STL/CLR)

両方の並べ替えられたソース範囲に属するすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `set_intersection` ます。 詳細については、「 [set_intersection](../standard-library/algorithm-functions.md#set_intersection)」を参照してください。

## <a name="set_symmetric_difference-stlclr"></a><a name="set_symmetric_difference"></a> set_symmetric_difference (STL/CLR)

並べ替えられたソース範囲の一方には属するが、両方には属さないすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `set_symmetric_difference` ます。 詳細については、「 [set_symmetric_difference](../standard-library/algorithm-functions.md#set_symmetric_difference)」を参照してください。

## <a name="set_union-stlclr"></a><a name="set_union"></a> set_union (STL/CLR)

2 つの並べ替えられたソース範囲の少なくとも一方に属するすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。

### <a name="syntax"></a>構文

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `set_union` ます。 詳細については、「 [set_union](../standard-library/algorithm-functions.md#set_union)」を参照してください。

## <a name="sort-stlclr"></a><a name="sort"></a> sort (STL/CLR)

指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って配置します。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void sort(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `sort` ます。 詳細については、「 [sort](../mfc/reference/cmfclistctrl-class.md#sort)」を参照してください。

## <a name="sort_heap-stlclr"></a><a name="sort_heap"></a> sort_heap (STL/CLR)

ヒープを並べ替えられた範囲に変換します。

### <a name="syntax"></a>構文

```cpp
template<class _RanIt> inline
    void sort_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void sort_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `sort_heap` ます。 詳細については、「 [sort_heap](../standard-library/algorithm-functions.md#sort_heap)」を参照してください。

## <a name="stable_partition-stlclr"></a><a name="stable_partition"></a> stable_partition (STL/CLR)

範囲内の要素を 2 つの分離されたセットに分類し、等価要素の相対順序は維持して、単項述語を満たす要素が単項述語を満たさない要素よりも前に来るように配置します。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt, class _Pr> inline
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `stable_partition` ます。 詳細については、「 [stable_partition](../standard-library/algorithm-functions.md#stable_partition)」を参照してください。

## <a name="stable_sort-stlclr"></a><a name="stable_sort"></a> stable_sort (STL/CLR)

指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、等価要素の相対順序を維持して配置します。

### <a name="syntax"></a>構文

```cpp
template<class _BidIt> inline
    void stable_sort(_BidIt _First, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `stable_sort` ます。 詳細については、「 [stable_sort](../standard-library/algorithm-functions.md#stable_sort)」を参照してください。

## <a name="swap-stlclr"></a><a name="swap"></a> swap (STL/CLR)

2 種類のオブジェクトの間で、最初のオブジェクトの内容を 2 番目のオブジェクトに割り当て、2 番目のオブジェクトの内容を最初のオブジェクトに割り当てて、要素の値を交換します。

### <a name="syntax"></a>構文

```cpp
<class _Ty> inline
    void swap(_Ty% _Left, _Ty% _Right);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `swap` ます。 詳細については、「 [swap](../standard-library/algorithm-functions.md#swap)」を参照してください。

## <a name="swap_ranges-stlclr"></a><a name="swap_ranges"></a> swap_ranges (STL/CLR)

1 つの範囲の要素を、同じサイズの別の範囲の要素と交換します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt2 swap_ranges(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `swap_ranges` ます。 詳細については、「 [swap_ranges](../standard-library/algorithm-functions.md#swap_ranges)」を参照してください。

## <a name="transform-stlclr"></a><a name="transform"></a> 変換 (STL/CLR)

指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をターゲット範囲にコピーします。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt, class _Fn1> inline
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Fn1 _Func);
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `transform` ます。 詳細については、「 [transform](../standard-library/algorithm-functions.md#transform)」を参照してください。

## <a name="unique-stlclr"></a><a name="unique"></a> 一意 (STL/CLR)

指定された範囲内の互いに隣接する重複要素を削除します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt> inline
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `unique` ます。 詳細については、「 [unique](../standard-library/algorithm-functions.md#unique)」を参照してください。

## <a name="unique_copy-stlclr"></a><a name="unique_copy"></a> unique_copy (STL/CLR)

互いに隣接する重複要素を除き、ソース範囲の要素をターゲット範囲にコピーします。

### <a name="syntax"></a>構文

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);
template<class _InIt, class _OutIt, class _Pr> inline
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `unique_copy` ます。 詳細については、「 [unique_copy](../standard-library/algorithm-functions.md#unique_copy)」を参照してください。

## <a name="upper_bound-stlclr"></a><a name="upper_bound"></a> upper_bound (STL/CLR)

順序の基準が二項述語で指定できる場合に、順序付けられた範囲内で、指定した値を超える値を持つ最初の要素の位置を検索します。

### <a name="syntax"></a>構文

```cpp
template<class _FwdIt, class _Ty> inline
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>解説

この関数は、C++ 標準ライブラリ関数と同じように動作し `upper_bound` ます。 詳細については、「 [upper_bound](../standard-library/algorithm-functions.md#upper_bound)」を参照してください。
