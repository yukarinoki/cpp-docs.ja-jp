---
title: '&lt;vector&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: 71594b225c950714d8b9aba169e68804033c93a2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700753"
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 関数


## <a name="swap"></a>  swap

2 つのベクターの要素を交換します。

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
交換する要素を提供するベクター、または要素のベクターと交換するベクター*左*します。

*left*<br/>
要素のベクターと交換するベクター*右*します。

### <a name="remarks"></a>Remarks

テンプレート関数はメンバー関数の実行に、コンテナー クラス ベクターに特化したアルゴリズム`left`します。 [vector::swap](../standard-library/vector-class.md) *(右*)。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。

### <a name="example"></a>例

テンプレート バージョンの `swap` の使用例については、メンバー関数 [vector::swap](../standard-library/vector-class.md) のコード例をご覧ください。

## <a name="see-also"></a>関連項目

[\<vector>](../standard-library/vector.md)<br/>
