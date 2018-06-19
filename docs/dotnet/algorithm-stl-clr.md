---
title: アルゴリズム (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/algorithm>
dev_langs:
- C++
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 30e347905c6802e544cb9f81c045f9cc881f29fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111329"
---
# <a name="algorithm-stlclr"></a>algorithm (STL/CLR)
アルゴリズムを実行する STL/CLR コンテナーのテンプレート関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <cliext/algorithm>  
```  
  
## <a name="functions"></a>関数  
  
|関数|説明|  
|--------------|-----------------|  
|[adjacent_find (STL/CLR)](../dotnet/adjacent-find-stl-clr.md)|等しい 2 つの隣接する要素を検索します。|  
|[binary_search (STL/CLR)](../dotnet/binary-search-stl-clr.md)|並べ替えられたシーケンスに指定された値があるかどうかをテストします。|  
|[copy (STL/CLR)](../dotnet/copy-stl-clr.md)|ソース範囲から値を前方に反復処理する、ターゲットの範囲にコピーします。|  
|[copy_backward (STL/CLR)](../dotnet/copy-backward-stl-clr.md)|ソース範囲から値を逆方向に繰り返し処理で、ターゲットの範囲にコピーします。|  
|[count (STL/CLR)](../dotnet/count-stl-clr.md)|範囲内で値が指定された値と一致する要素の数を返します。|  
|[count_if (STL/CLR)](../dotnet/count-if-stl-clr.md)|範囲内で値が指定された条件と一致する要素の数を返します。|  
|[equal (STL/CLR)](../dotnet/equal-stl-clr.md)|2 つの範囲、要素ごとに比較します。|  
|[equal_range (STL/CLR)](../dotnet/equal-range-stl-clr.md)|値の順序付けられたシーケンスを検索し、指定された要素と等しいすべての値のサブシーケンスを区切るための 2 つの位置を返します。|  
|[fill (STL/CLR)](../dotnet/fill-stl-clr.md)|指定された範囲のすべての要素に同じ新しい値を割り当てます。|  
|[fill_n (STL/CLR)](../dotnet/fill-n-stl-clr.md)|特定の要素で始まる要素範囲で、指定された数の要素に新しい値を割り当てます。|  
|[find (STL/CLR)](../dotnet/find-stl-clr.md)|指定された値の最初に見つかった位置の位置を返します。|  
|[find_end (STL/CLR)](../dotnet/find-end-stl-clr.md)|指定されたシーケンスと同じである範囲の最後のサブシーケンスを返します。|  
|[find_first_of (STL/CLR)](../dotnet/find-first-of-stl-clr.md)|指定された範囲の要素のいずれかの最初に見つかった位置の範囲を検索します。|  
|[find_if (STL/CLR)](../dotnet/find-if-stl-clr.md)|要素が、指定した条件を満たす値のシーケンスの最初の要素の位置を返します。|  
|[for_each (STL/CLR)](../dotnet/for-each-stl-clr.md)|値のシーケンス内の各要素に指定された関数オブジェクトを適用し、関数オブジェクトを返します。|  
|[generate (STL/CLR)](../dotnet/generate-stl-clr.md)|値のシーケンス内の各要素に関数オブジェクトによって生成された値を割り当てます。|  
|[generate_n (STL/CLR)](../dotnet/generate-n-stl-clr.md)|指定した数の要素に関数オブジェクトによって生成された値を割り当てます。|  
|[includes (STL/CLR)](../dotnet/includes-stl-clr.md)|1 つの並べ替えられた範囲内に 2 番目の並べ替えられた範囲内のすべての要素があるかどうかをテストします。|  
|[inplace_merge (STL/CLR)](../dotnet/inplace-merge-stl-clr.md)|2 つの連続する並べ替えられた範囲の要素を単一の並べ替えられた範囲に結合します。|  
|[iter_swap (STL/CLR)](../dotnet/iter-swap-stl-clr.md)|指定された反復子のペアで参照される 2 個の値を交換します。|  
|[lexicographical_compare (STL/CLR)](../dotnet/lexicographical-compare-stl-clr.md)|どのシーケンスが、2 つのうち、小さい方を識別する、要素が要素 2 つのシーケンスを比較します。|  
|[lower_bound (STL/CLR)](../dotnet/lower-bound-stl-clr.md)|指定した値以上の値を持つ値の順序付けられたシーケンス内の最初の要素の位置を検索します。|  
|[make_heap (STL/CLR)](../dotnet/make-heap-stl-clr.md)|要素を指定された範囲をヒープ上の最初の要素が最大ヒープに変換します。|  
|[max (STL/CLR)](../dotnet/max-stl-clr.md)|2 つのオブジェクトを比較し、2 つの大きい方を返します。|  
|[max_element (STL/CLR)](../dotnet/max-element-stl-clr.md)|値の指定されたシーケンス内で最も大きな要素を検索します。|  
|[merge (STL/CLR)](../dotnet/merge-stl-clr.md)|2 つの並べ替えられたソース範囲からのすべての要素を単一の並べ替えられたターゲット範囲に結合します。|  
|[min (STL/CLR)](../dotnet/min-stl-clr.md)|2 つのオブジェクトを比較し、2 つのうち、小さい方を返します。|  
|[min_element (STL/CLR)](../dotnet/min-element-stl-clr.md)|値の指定されたシーケンスの最小の要素を検索します。|  
|[mismatch (STL/CLR)](../dotnet/mismatch-stl-clr.md)|2 つの範囲を要素ごとに比較し、違いが発生する最初の位置を返します。|  
|[next_permutation (STL/CLR)](../dotnet/next-permutation-stl-clr.md)|ように、元の順序を辞書式に次に大きい順列が存在する場合は、範囲内の要素を並べ替えます。|  
|[nth_element (STL/CLR)](../dotnet/nth-element-stl-clr.md)|正しくを検索する要素のシーケンスをパーティション分割、`n`番目の要素シーケンスの前にすべての要素は、以下に、それに続くすべての要素より大きいか等しいことをできるようにします。|  
|[partial_sort (STL/CLR)](../dotnet/partial-sort-stl-clr.md)|降順以外の順序を指定した範囲内の小さい要素数を配置します。|  
|[partial_sort_copy (STL/CLR)](../dotnet/partial-sort-copy-stl-clr.md)|ソース範囲の要素は順序付けになるようにターゲット範囲に、ソース範囲から要素をコピーします。|  
|[partition (STL/CLR)](../dotnet/partition-stl-clr.md)|単項述語を満たす要素の前にそれを満たさないものになるように、範囲内の要素を整列します。|  
|[pop_heap (STL/CLR)](../dotnet/pop-heap-stl-clr.md)|ヒープの先頭から最大の要素を末尾に移動し、残りの要素から新しいヒープを形成します。|  
|[prev_permutation (STL/CLR)](../dotnet/prev-permutation-stl-clr.md)|ように、元の順序を辞書式の前に大きい順列が存在する場合は、要素のシーケンスを並べ替えます。|  
|[push_heap (STL/CLR)](../dotnet/push-heap-stl-clr.md)|範囲の末尾にある要素を、範囲内の以前の要素で構成される既存のヒープに追加します。|  
|[random_shuffle (STL/CLR)](../dotnet/random-shuffle-stl-clr.md)|シーケンスを並べ替えます`N`のいずれかに範囲内の要素`N`! 個の可能な配置の 1 つに再配置します。|  
|[remove (STL/CLR)](../dotnet/remove-stl-clr.md)|特定の範囲から、残りの要素の順序の影響を及ぼすことがなく、指定した値を削除し、指定された値を含まない新しい範囲の末尾を返します。|  
|[remove_copy (STL/CLR)](../dotnet/remove-copy-stl-clr.md)|残りの要素の順序の影響を及ぼすことがなく、指定された値の要素はコピーされないことを除き、要素をターゲット範囲に、ソース範囲からコピーします。|  
|[remove_copy_if (STL/CLR)](../dotnet/remove-copy-if-stl-clr.md)|ソース範囲から述語を満たす、残りの要素の順序の影響を及ぼすことがなくものを除き、ターゲットの範囲に要素をコピーします。|  
|[remove_if (STL/CLR)](../dotnet/remove-if-stl-clr.md)|残りの要素の順序の影響を及ぼすことがなく、指定された範囲から述語を満たす要素を削除します。 である必要があります。|  
|[replace (STL/CLR)](../dotnet/replace-stl-clr.md)|新しい値を持つ指定した値と一致する範囲内の要素を置き換えます。|  
|[replace_copy (STL/CLR)](../dotnet/replace-copy-stl-clr.md)|ソース範囲から新しい値を持つ指定した値と一致する要素を置換、ターゲットの範囲に要素をコピーします。|  
|[replace_copy_if (STL/CLR)](../dotnet/replace-copy-if-stl-clr.md)|ソース範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えて結果を新しいターゲット範囲にコピーします。|  
|[replace_if (STL/CLR)](../dotnet/replace-if-stl-clr.md)|範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えます。|  
|[reverse (STL/CLR)](../dotnet/reverse-stl-clr.md)|範囲内の要素の順序を反転させます。|  
|[reverse_copy (STL/CLR)](../dotnet/reverse-copy-stl-clr.md)|ターゲット範囲にコピーします。 ソース範囲内の要素の順序を反転します。|  
|[rotate (STL/CLR)](../dotnet/rotate-stl-clr.md)|2 つの隣接する範囲の要素を交換します。|  
|[rotate_copy (STL/CLR)](../dotnet/rotate-copy-stl-clr.md)|ソース範囲内の 2 つの隣接する範囲の要素を交換し、結果をターゲット範囲にコピーします。|  
|[search (STL/CLR)](../dotnet/search-stl-clr.md)|要素が特定の要素シーケンス内の要素と等しいか、または要素が二項述語で指定される意味において特定のシーケンス内の要素と等価であるシーケンスが、対象範囲内で最初に出現する位置を検索します。|  
|[search_n (STL/CLR)](../dotnet/search-n-stl-clr.md)|特定の値を持つか、二項述語によって指定される値と関連する、指定された数の要素で構成される範囲内の最初のサブシーケンスを検索します。|  
|[set_difference (STL/CLR)](../dotnet/set-difference-stl-clr.md)|1 つの並べ替えられたソース範囲内に属するが、2 番目の並べ替えられたソース範囲には属さないすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|  
|[set_intersection (STL/CLR)](../dotnet/set-intersection-stl-clr.md)|両方の並べ替えられたソース範囲に属するすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|  
|[set_symmetric_difference (STL/CLR)](../dotnet/set-symmetric-difference-stl-clr.md)|並べ替えられたソース範囲の一方には属するが、両方には属さないすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|  
|[set_union (STL/CLR)](../dotnet/set-union-stl-clr.md)|2 つの並べ替えられたソース範囲の少なくとも一方に属するすべての要素を単一の並べ替えられたターゲット範囲として結合します。順序の基準は二項述語によって指定できます。|  
|[sort (STL/CLR)](../dotnet/sort-stl-clr.md)|指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って配置します。|  
|[sort_heap (STL/CLR)](../dotnet/sort-heap-stl-clr.md)|ヒープを並べ替えられた範囲に変換します。|  
|[stable_partition (STL/CLR)](../dotnet/stable-partition-stl-clr.md)|範囲内の要素を 2 つの分離されたセットに分類し、等価要素の相対順序は維持して、単項述語を満たす要素が単項述語を満たさない要素よりも前に来るように配置します。|  
|[stable_sort (STL/CLR)](../dotnet/stable-sort-stl-clr.md)|指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、等価要素の相対順序を維持して配置します。|  
|[swap (STL/CLR)](../dotnet/swap-stl-clr.md)|2 種類のオブジェクトの間で、最初のオブジェクトの内容を 2 番目のオブジェクトに割り当て、2 番目のオブジェクトの内容を最初のオブジェクトに割り当てて、要素の値を交換します。|  
|[swap_ranges (STL/CLR)](../dotnet/swap-ranges-stl-clr.md)|1 つの範囲の要素を、同じサイズの別の範囲の要素と交換します。|  
|[transform (STL/CLR)](../dotnet/transform-stl-clr.md)|指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をターゲット範囲にコピーします。|  
|[unique (STL/CLR)](../dotnet/unique-stl-clr.md)|指定された範囲内の互いに隣接する重複要素を削除します。|  
|[unique_copy (STL/CLR)](../dotnet/unique-copy-stl-clr.md)|互いに隣接する重複要素を除き、ソース範囲の要素をターゲット範囲にコピーします。|  
|[upper_bound (STL/CLR)](../dotnet/upper-bound-stl-clr.md)|順序の基準が二項述語で指定できる場合に、順序付けられた範囲内で、指定した値を超える値を持つ最初の要素の位置を検索します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)