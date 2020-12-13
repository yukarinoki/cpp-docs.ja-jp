---
description: '詳細情報: &lt; set &gt; 関数'
title: '&lt;set&gt; 系関数'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: 14f8eac3f725f88d98cdba133dace06993e5c089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154137"
---
# <a name="ltsetgt-functions"></a>&lt;set&gt; 系関数

## <a name="swap-map"></a><a name="swap"></a> スワップ (マップ)

2 つの set の要素を交換します。

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する要素を提供するセット。または、要素が設定された *左側* の要素と交換されるセット。

*左側*\
セット *権限* と要素が交換されるセット。

### <a name="remarks"></a>解説

このテンプレート関数は、メンバー関数 `left.` [swap](../standard-library/set-class.md#swap)() を実行するように設定されたコンテナークラスに特化したアルゴリズムです `right` 。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template`\< **classT**> **void swap**( **t&**、 **t&**)

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [set::swap](../standard-library/set-class.md#swap) のコード例をご覧ください。

## <a name="swap-multiset"></a><a name="swap_multiset"></a> スワップ (マルチセット)

2 つの multiset の要素を交換します。

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する要素を提供するマルチセット、または要素がマルチセットの *左側* と交換されるマルチセット。

*左側*\
要素がマルチセット *右* の要素と交換されるマルチセット。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラスのマルチセットに特化したアルゴリズムで、メンバー関数 `left.` [swap](../standard-library/multiset-class.md#swap)() を実行し `right` ます。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template`\< **classT**> **void swap**( **t&**、 **t&**)

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

`swap` のテンプレート バージョンの使用例については、メンバー クラス [multiset::swap](../standard-library/multiset-class.md#swap) のコード例をご覧ください。
