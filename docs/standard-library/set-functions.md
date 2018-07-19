---
title: '&lt;set&gt; 系関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: b25194dc1cdc45bc93d9e5188715e3ea01258af4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966333"
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

*適切な*を交換する要素を提供するセットまたはセットと交換される要素がセット*左*します。

*左*のセットと交換される要素がセット*右*します。

### <a name="remarks"></a>Remarks

テンプレート関数は、コンテナー クラス set メンバー関数の実行に特化したアルゴリズム`left.`[スワップ](../standard-library/set-class.md#swap)(`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

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

*適切な*を交換する要素を提供する multiset または要素が multiset と交換される multiset*左*します。

*左*要素が multiset と交換される multiset*右*します。

### <a name="remarks"></a>Remarks

テンプレート関数はメンバー関数を実行するコンテナー クラス multiset に特化したアルゴリズム`left.`[スワップ](../standard-library/multiset-class.md#swap)(`right`)。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template` \< **classT**> **void swap**( **T&**, **T&**)

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [multiset::swap](../standard-library/multiset-class.md#swap) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[\<set>](../standard-library/set.md)<br/>
