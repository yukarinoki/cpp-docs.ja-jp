---
title: '&lt;set&gt; 系関数'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: a3a63fb86caa3485b1ee14538c3eb1f1ff72923e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78875768"
---
# <a name="ltsetgt-functions"></a>&lt;set&gt; 系関数

## <a name="swap"></a>スワップ (マップ)

2 つの set の要素を交換します。

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*右*\
交換する要素を提供するセット。または、要素が設定された*左側*の要素と交換されるセット。

*左*\
セット*権限*と要素が交換されるセット。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラスに特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/set-class.md#swap)(`right`) を実行するように設定されています。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template` \< **classT**> **void swap**( **t &** 、 **t &** )

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

[ のテンプレート バージョンの使用例については、メンバー クラス ](../standard-library/set-class.md#swap)set::swap`swap` のコード例をご覧ください。

## <a name="swap_multiset"></a>スワップ (マルチセット)

2 つの multiset の要素を交換します。

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*右*\
交換する要素を提供するマルチセット、または要素がマルチセットの*左側*と交換されるマルチセット。

*左*\
要素がマルチセット*右*の要素と交換されるマルチセット。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラスのマルチセットに特化したアルゴリズムであり、`left.`[スワップ](../standard-library/multiset-class.md#swap)(`right`) のメンバー関数を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン

`template` \< **classT**> **void swap**( **t &** 、 **t &** )

は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

[ のテンプレート バージョンの使用例については、メンバー クラス ](../standard-library/multiset-class.md#swap)multiset::swap`swap` のコード例をご覧ください。
