---
title: 論理 AND 演算子:&amp;&amp;
description: C++ 標準言語の論理 AND 演算子の構文とを使用します。
ms.date: 07/23/2020
f1_keywords:
- '&&'
- and_cpp
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: 431e76a2943c2373d6191f1fbe9f14c54cfaa6c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223695"
---
# <a name="logical-and-operator-ampamp"></a>論理 AND 演算子:&amp;&amp;

## <a name="syntax"></a>構文

> *式* **`&&`***式*

## <a name="remarks"></a>解説

論理 AND 演算子 ( **&&** ) は、 **`true`** 両方のオペランドがである場合はを返し、それ以外の場合はを返し **`true`** **`false`** ます。 オペランドは評価前に型に暗黙的に変換され、 **`bool`** 結果は型になり **`bool`** ます。 論理 AND には左から右方向の結合規則があります。

論理 AND 演算子のオペランドは、同じ型である必要はありませんが、ブール型、整数型、またはポインター型である必要があります。 オペランドは一般に関係式または等価式です。

最初のオペランドは完全に評価され、論理 AND 式の評価が続行される前にすべての副作用が完了します。

2番目のオペランドは、最初のオペランドが (0 以外) に評価された場合にのみ評価され **`true`** ます。 この評価により、論理 AND 式がの場合、2番目のオペランドの不要な評価が不要になり **`false`** ます。 このショート サーキット評価を使用して、次の例に示すように、null ポインターの逆参照を防止できます。

```cpp
char *pch = 0;
// ...
(pch) && (*pch = 'a');
```

`pch` が null (0) であれば、式の右側は評価されません。 このショートサーキット評価では、null ポインターを使用して割り当てを行うことはできません。

## <a name="operator-keyword-for-"></a> && の Operator キーワード

C++ **`and`** では、の代替スペルとしてを指定し **`&&`** ます。 C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_Logical_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate logical AND
#include <iostream>

using namespace std;

int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b && b < c yields "
         << (a < b && b < c) << endl
         << "The false expression "
         << "a > b && b < c yields "
         << (a > b && b < c) << endl;
}
```

## <a name="see-also"></a>関連項目

[C++ の組み込み演算子、優先順位、および結合規則](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 論理演算子](../c-language/c-logical-operators.md)
