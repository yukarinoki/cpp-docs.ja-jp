---
description: '詳細情報: hash_compare クラス'
title: hash_compare クラス
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 510de9901e58e130a53410b688c22324714b9962
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231941"
---
# <a name="hash_compare-class"></a>hash_compare クラス

クラステンプレートは、任意のハッシュ連想コンテナー (hash_map、hash_multimap、hash_set、または hash_multiset) で使用できるオブジェクトを表します。このオブジェクトには、含まれる要素の順序付けとハッシュを行う既定の **特徴** パラメーターオブジェクトとして使用できます。

## <a name="syntax"></a>構文

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>解説

各ハッシュ連想コンテナーは、型のハッシュ特性オブジェクト `Traits` (テンプレートパラメーター) を格納します。 特定の関数とオブジェクトを選択的にオーバーライドするために hash_compare を特殊化してクラスを派生させるか、特定の最小要件を満たしているこのクラスの独自のバージョンを使用することができます。 具体的には、型のオブジェクト hash_comp の場合、 `hash_compare<Key, Traits>` 上記のコンテナーでは次の動作が必要です。

- 型のすべての値について `key` `Key` 、呼び出し **hash_comp**( `key` ) はハッシュ関数として機能します。これにより、型の値の分布が生成さ `size_t` れます。 hash_compare によって提供される関数は `key` を返します。

- `key1` `Key` シーケンスの前 `key2` にあり、同じハッシュ値 (ハッシュ関数によって返される値) を持つ型の値については、 **hash_comp**( `key2` , `key1` ) は false になります。 関数は、型の値に対して合計の順序付けを強制する必要があり `Key` ます。 Hash_compare によって提供される関数は *comp*( `key2` ,) を返し `key1` `,` ます。ここで、 *comp* は、 `Traits` オブジェクト hash_comp を構築するときに指定できる型の格納されたオブジェクトです。 既定の `Traits` パラメーター型では `less<Key>` 、並べ替えキーの値が減少することはありません。

- 整数定数は、 `bucket_size` コンテナーが超えないようにする必要がある "バケット" (ハッシュテーブルエントリ) あたりの要素の平均数を指定します。 0 より大きくなければなりません。 hash_compare によって提供される値は 4 です。

- 整数定数は、 `min_buckets` ハッシュテーブルで保持するバケットの最小数を指定します。 2 の累乗で、0 より大きくなければなりません。 hash_compare によって提供される値は 8 です。

## <a name="example"></a>例

hash_compare の宣言方法や使用方法の例については、[hash_map::hash_map](../standard-library/hash-map-class.md#hash_map)[hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap)[hash_set::hash_set](../standard-library/hash-set-class.md#hash_set)および [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset) の例をご覧ください。

## <a name="requirements"></a>要件

**ヘッダー:**\<hash_map>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
