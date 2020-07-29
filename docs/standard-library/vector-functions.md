---
title: '&lt;vector&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: bf28e44b4f603b1e4d6a87f0c28b42d6cc159980
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224553"
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 関数

## <a name="swap"></a><a name="swap"></a>フォト

2 つのベクターの要素を交換します。

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する要素を提供*するベクター、* またはベクターの要素と交換される要素を持つベクター。

*左側*\
ベクター*右*の要素と交換される要素を持つベクター。

### <a name="remarks"></a>解説

このテンプレート関数は、コンテナークラスの vector に特化したアルゴリズムで、メンバー関数を実行し `left` ます。 [vector:: swap](../standard-library/vector-class.md) *(right*)。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 アルゴリズムクラスの一般的なバージョンのテンプレート関数である **`template`** \< **class T**> **void swap**( **t&**、 **t&**) は、割り当てによって動作し、処理が遅くなります。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

テンプレート バージョンの `swap` の使用例については、メンバー関数 [vector::swap](../standard-library/vector-class.md) のコード例をご覧ください。
