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
ms.openlocfilehash: eb1e42bf61c1fa70ee74063cd6857d842ee87de7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846494"
---
# <a name="hashcompare-class"></a>hash_compare クラス

テンプレート クラスは、任意のハッシュ連想コンテナー (hash_map、hash_multimap、hash_set、hash_multiset) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。

## <a name="syntax"></a>構文

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>コメント

各ハッシュ連想コンテナーは、**Traits** 型のハッシュ特性 オブジェクト (テンプレート パラメーター) を格納します。 特定の関数とオブジェクトを選択的に無視するために hash_compare を特殊化してクラスを派生させるか、特定の最小要件を満たしているこのクラスの独自のバージョンを使用することができます。 具体的には、**hash_compare\<Key, Traits>** 型のオブジェクト hash_comp について、上記のコンテナーで次の動作が必要です。

- **Key** 型のすべての値 `key` について、呼び出し **hash_comp** (`key`) はハッシュ関数として機能し、**size_t** 型の値の分布を生成します。 hash_compare によって提供される関数は `key` を返します。

- 並べ替え順序において `key2` の前になる、同じハッシュ値 (ハッシュ関数によって返される値) を持つ **Key** 型の任意の値 `key1` について、**hash_comp** (`key2`、`key1`) は false になります。 関数は、**Key** 型の値の完全な順序付けを強制する必要があります。 hash_compare によって提供される関数は *comp* (`key2`、`key1`) `,` を返します。ここで、*comp* は **Traits** 型の格納されているオブジェクトを示し、オブジェクト hash_comp を構築する際に指定できます。 既定の **Traits** パラメーター型 **less\<Key>** について、並べ替えキーの値が減少することはありません。

- 整数の定数 **bucket_size** は、コンテナーが超えるべきでない、「バケット」(ハッシュ テーブルのエントリ) ごとの要素の平均数を指定します。 0 より大きくなければなりません。 hash_compare によって提供される値は 4 です。

- 整数の定数 **min_buckets** は、ハッシュ テーブルに保持するバケットの最小数を指定します。 2 の累乗で、0 より大きくなければなりません。 hash_compare によって提供される値は 8 です。

## <a name="example"></a>例

hash_compare の宣言方法や使用方法の例については、[hash_map::hash_map](../standard-library/hash-map-class.md#hash_map)[hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap)[hash_set::hash_set](../standard-library/hash-set-class.md#hash_set)および [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset) の例をご覧ください。

## <a name="requirements"></a>要件

**ヘッダー:** \<hash_map>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
