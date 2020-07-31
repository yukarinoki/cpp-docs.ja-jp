---
title: '論理否定演算子: !'
description: C++ 標準言語の論理否定演算子の構文とを使用します。
ms.date: 07/23/2020
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: fdd2e7a71b791375f898372d058a5eeb2afc59f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223682"
---
# <a name="logical-negation-operator-"></a>論理否定演算子: !

## <a name="syntax"></a>構文

> **`!`***キャスト式*

## <a name="remarks"></a>解説

論理否定演算子 () は、 **`!`** オペランドの意味を反転させます。 オペランドは、数値型またはポインター型 (または、数値型またはポインター型に評価される式) である必要があります。 オペランドは型に暗黙的に変換され **`bool`** ます。 変換されたオペランドがの場合、結果はになります。変換されたオペランドがの場合、結果はになり **`true`** **`false`** **`false`** **`true`** ます。 結果は型 **`bool`** です。

式の場合、 `e` 単項式 `!e` は、 `(e == 0)` オーバーロードされた演算子が関係する場合を除き、式に相当します。

## <a name="operator-keyword-for-"></a>! の演算子キーワード

C++ **`not`** では、の代替スペルとしてを指定し **`!`** ます。 C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[単項算術演算子](../c-language/unary-arithmetic-operators.md)<br/>
