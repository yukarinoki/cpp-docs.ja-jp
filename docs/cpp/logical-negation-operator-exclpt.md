---
title: '論理否定演算子: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 06142ef15fcdbafdbae4b892772a04b117c087f6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446541"
---
# <a name="logical-negation-operator-"></a>論理否定演算子: !

## <a name="syntax"></a>構文

```
! cast-expression
```

## <a name="remarks"></a>コメント

論理否定演算子 ( **!** ) は、オペランドの意味を反転させます。 オペランドは、数値型またはポインター型 (または、数値型またはポインター型に評価される式) である必要があります。 オペランドは暗黙的に**ブール**型に変換されます。 変換されたオペランドが FALSE の場合、結果は TRUE になります。変換されたオペランドが TRUE の場合、結果は FALSE になります。 結果は**bool**型になります。

式*e*の場合、単項式 `!e` は、オーバーロードされた演算子が関係する場合を除き、`(e == 0)`式に相当します。

## <a name="operator-keyword-for-"></a>! の演算子キーワード

**Not**演算子は、 **!** の代わりのスペルです。 プログラム内の**not**演算子にアクセスするには、次の2つの方法があります。ヘッダーファイル \<iso646 > を含めるか、または[/za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張機能を無効にする) コンパイラオプションを使用してコンパイルします。

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

## <a name="see-also"></a>参照

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[単項算術演算子](../c-language/unary-arithmetic-operators.md)<br/>
