---
title: '&lt;hash_set&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 083d928198d8d83d8a56d8a74a6204e94c86aa67
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; 関数

|||
|-|-|
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>  swap

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。

2 つの hash_set の要素を交換します。

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`right` 交換する要素を提供する、hash_set、または hash_set のものと交換される要素は、hash_set`left`です。

`left` Hash_set のものと交換される要素は、hash_set`right`です。

### <a name="remarks"></a>コメント

`swap` テンプレート関数は、コンテナー クラス hash_set に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/hash-set-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

**template \<class T> void swap(T&, T&),**

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_set::swap](../standard-library/hash-set-class.md#swap) のコード例をご覧ください。

## <a name="swap_hash_multiset"></a> swap (hash_multiset)

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。

2 つの hash_multiset の要素を交換します。

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`right` 交換する要素を提供する hash_multiset またはと交換される hash_multiset の要素が hash_multiset`left`です。

`left` Hash_multiset のものと交換される要素は、hash_multiset`right`です。

### <a name="remarks"></a>コメント

`swap` テンプレート関数は、コンテナー クラス hash_multiset に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/hash-multiset-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

**template \<class T> void swap(T&, T&),**

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[<hash_set>](../standard-library/hash-set.md)<br/>
