---
title: '&lt;hash_set&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: d7df6b3c5dc0d0d493d17b3e9995bc4758ffd6d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370585"
---
# <a name="lthash_setgt-functions"></a>&lt;hash_set&gt; 関数

|||
|-|-|
|[スワップ](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a><a name="swap"></a>スワップ

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。

2 つの hash_set の要素を交換します。

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
hash_set、スワップする要素を提供する要素、または要素を*左*hash_setの要素と交換するhash_set。

*左*\
要素がhash_set*権利*の要素と交換されるhash_set.

### <a name="remarks"></a>解説

テンプレート`swap`関数は、メンバー関数`left.`[のスワップ](../standard-library/hash-set-class.md#swap)( )`right`を実行するhash_setコンテナー クラスに特化したアルゴリズムです。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

**template \<class T> void swap(T&, T&),**

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_set::swap](../standard-library/hash-set-class.md#swap) のコード例をご覧ください。

## <a name="swap-hash_multiset"></a><a name="swap_hash_multiset"></a>スワップ (hash_multiset)

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。

2 つの hash_multiset の要素を交換します。

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
hash_multiset交換する要素を提供する要素、または要素を*左*hash_multisetの要素と交換するhash_multiset。

*左*\
要素をhash_multiset*権利*の要素と交換するhash_multiset。

### <a name="remarks"></a>解説

テンプレート`swap`関数は、メンバー関数`left.`[のスワップ](../standard-library/hash-multiset-class.md#swap)( )`right`を実行するためにhash_multisetコンテナ クラスに特化したアルゴリズムです。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

**template \<class T> void swap(T&, T&),**

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[<hash_set>](../standard-library/hash-set.md)
