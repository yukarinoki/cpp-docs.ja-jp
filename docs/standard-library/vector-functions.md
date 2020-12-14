---
description: '詳細情報: &lt; vector &gt; 関数'
title: '&lt;vector&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: c59e2626a2062be90d2cb8201b058d5ee148ef55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187885"
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 関数

## <a name="swap"></a><a name="swap"></a> フォト

2 つのベクターの要素を交換します。

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する要素を提供 *するベクター、* またはベクターの要素と交換される要素を持つベクター。

*左側*\
ベクター *右* の要素と交換される要素を持つベクター。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラスの vector に特化したアルゴリズムで、メンバー関数を実行し `left` ます。 [vector:: swap](../standard-library/vector-class.md) *(right*)。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 アルゴリズムクラスの一般的なバージョンのテンプレート関数である **`template`** \< **class T**> **void swap**( **t&**、 **t&**) は、割り当てによって動作し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

テンプレート バージョンの `swap` の使用例については、メンバー関数 [vector::swap](../standard-library/vector-class.md) のコード例をご覧ください。
