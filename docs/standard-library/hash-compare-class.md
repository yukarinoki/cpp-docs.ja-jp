---
title: hash_compare クラス
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 399b412c41128f513cf01d1e034bad2bbc5ef79f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448805"
---
# <a name="hashcompare-class"></a>hash_compare クラス

テンプレート クラスは、任意のハッシュ連想コンテナー (hash_map、hash_multimap、hash_set、hash_multiset) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。

## <a name="syntax"></a>構文

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Remarks

各ハッシュ連想コンテナーは、型`Traits`のハッシュ特性オブジェクト (テンプレートパラメーター) を格納します。 特定の関数とオブジェクトを選択的にオーバーライドするために hash_compare を特殊化してクラスを派生させるか、特定の最小要件を満たしているこのクラスの独自のバージョンを使用することができます。 具体的には、型`hash_compare<Key, Traits>`のオブジェクト hash_comp の場合、上記のコンテナーには次の動作が必要です。

- `key`型`key` `size_t` のすべての値について、call hash_comp () はハッシュ関数として機能します。これにより、型の値の分布が生成されます。 `Key` hash_compare によって提供される関数は `key` を返します。

- シーケンスの前`key1` `key2` `key1` `Key` に`key2`あり、同じハッシュ値 (ハッシュ関数によって返される値) を持つ型の値の場合、 **hash_comp**(,) は false になります。 関数は、型`Key`の値に対して合計の順序付けを強制する必要があります。 Hash_compare によって提供される関数`key2`は`key1`comp `,` (  ,) を返します。ここ`Traits`で、comp は、オブジェクト hash_comp を構築するときに指定できる型の格納されたオブジェクトです。 既定`Traits`のパラメーター型`less<Key>`では、並べ替えキーの値が減少することはありません。

- 整数定数`bucket_size`は、コンテナーが超えないようにする必要がある "バケット" (ハッシュテーブルエントリ) あたりの要素の平均数を指定します。 0 より大きくなければなりません。 hash_compare によって提供される値は 4 です。

- 整数定数`min_buckets`は、ハッシュテーブルで保持するバケットの最小数を指定します。 2 の累乗で、0 より大きくなければなりません。 hash_compare によって提供される値は 8 です。

## <a name="example"></a>例

hash_compare の宣言方法や使用方法の例については、[hash_map::hash_map](../standard-library/hash-map-class.md#hash_map)[hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap)[hash_set::hash_set](../standard-library/hash-set-class.md#hash_set)および [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset) の例をご覧ください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<hash_map>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
