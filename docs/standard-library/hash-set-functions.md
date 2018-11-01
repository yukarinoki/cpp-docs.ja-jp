---
title: '&lt;hash_set&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 05a7ffd1e3bf02a88fe6a6cce841a440550c1057
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551347"
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

*right*<br/>
Hash_set の要素を交換するには、提供する、または要素が hash_set と交換される hash_set*左*します。

*left*<br/>
要素が hash_set と交換される hash_set*右*します。

### <a name="remarks"></a>Remarks

`swap`テンプレート関数はメンバー関数を実行するコンテナー クラス hash_set に特化したアルゴリズム`left.`[スワップ](../standard-library/hash-set-class.md#swap)(`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

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

*right*<br/>
Hash_multiset の要素を交換するには、提供するか、含まれる要素が hash_multiset と交換される hash_multiset*左*します。

*left*<br/>
要素が hash_multiset と交換される hash_multiset*右*します。

### <a name="remarks"></a>Remarks

`swap`テンプレート関数はメンバー関数を実行するコンテナー クラス hash_multiset に特化したアルゴリズム`left.`[スワップ](../standard-library/hash-multiset-class.md#swap)(`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

**template \<class T> void swap(T&, T&),**

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[<hash_set>](../standard-library/hash-set.md)<br/>
