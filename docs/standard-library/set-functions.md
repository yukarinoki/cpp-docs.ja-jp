---
title: '&lt;set&gt; 系関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: aac2aaa09f609cd88c2bfab0e3fb66f4edade293
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltsetgt-functions"></a>&lt;set&gt; 系関数

|||
|-|-|
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|

## <a name="swap"></a>  swap  (map)

2 つの set の要素を交換します。

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`right` 交換する要素を提供するセットまたはセットのものと交換する要素は、セット`left`です。

`left` 要素と交換される、セットのセット`right`です。

### <a name="remarks"></a>コメント

テンプレート関数は、コンテナー クラス set に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/set-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template` \< **classT**> **void swap**( **T&**, **T&**)

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [set::swap](../standard-library/set-class.md#swap) のコード例をご覧ください。

## <a name="swap_multiset"></a>  swap  (multiset)

2 つの multiset の要素を交換します。

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`right` 交換する要素を提供する multiset またはと交換される multiset の要素が multiset`left`です。

`left` 交換される multiset の要素が multiset`right`です。

### <a name="remarks"></a>コメント

テンプレート関数は、コンテナー クラス multiset に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/multiset-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template` \< **classT**> **void swap**( **T&**, **T&**)

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [multiset::swap](../standard-library/multiset-class.md#swap) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[\<set>](../standard-library/set.md)<br/>
