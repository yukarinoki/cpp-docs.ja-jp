---
title: hash_compare クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_set/stdext::hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92dce97754eccc8cd4f618db3ac3e23574fb54ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956583"
---
# <a name="hashcompare-class"></a>hash_compare クラス

テンプレート クラスは、任意のハッシュ連想コンテナー (hash_map、hash_multimap、hash_set、hash_multiset) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。

## <a name="syntax"></a>構文

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Remarks

各ハッシュ連想コンテナーの種類のハッシュ特性オブジェクトを格納する`Traits`(テンプレート パラメーター)。 特定の関数とオブジェクトを選択的にオーバーライドするために hash_compare を特殊化してクラスを派生させるか、特定の最小要件を満たしているこのクラスの独自のバージョンを使用することができます。 具体的には、型のオブジェクト hash_comp についての`hash_compare<Key, Traits>`、上記のコンテナーで、次の動作が必要です。

- すべての値の`key`型の`Key`、呼び出し**hash_comp**(`key`) 型の値の分布を生成、ハッシュ関数として機能`size_t`します。 hash_compare によって提供される関数は `key` を返します。

- 任意の値の`key1`型の`Key`前になる`key2`シーケンスと同じハッシュ値 (ハッシュ関数によって返される値) **hash_comp**(`key2`、 `key1`) は false。 関数は、型の値で順序付けの合計を課す必要があります`Key`します。 Hash_compare によって提供される関数を返します*comp*(`key2`、 `key1`)`,`場所*comp*型の格納されているオブジェクトは、`Traits`ときに指定できることをオブジェクト hash_comp を構築します。 既定の`Traits`パラメーターの型`less<Key>`、並べ替えキーの値で減少することはありません。

- 整数の定数`bucket_size`を超えないようにしてください、コンテナーを「バケット」(ハッシュ テーブルのエントリ) ごとの要素の平均数を指定します。 0 より大きくなければなりません。 hash_compare によって提供される値は 4 です。

- 整数の定数`min_buckets`ハッシュ テーブルに保持するバケットの最小数を指定します。 2 の累乗で、0 より大きくなければなりません。 hash_compare によって提供される値は 8 です。

## <a name="example"></a>例

hash_compare の宣言方法や使用方法の例については、[hash_map::hash_map](../standard-library/hash-map-class.md#hash_map)[hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap)[hash_set::hash_set](../standard-library/hash-set-class.md#hash_set)および [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset) の例をご覧ください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<hash_map>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
