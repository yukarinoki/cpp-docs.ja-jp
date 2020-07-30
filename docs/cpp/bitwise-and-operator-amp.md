---
title: ビットごとの AND 演算子:&amp;
description: C++ 標準言語のビットごとの AND 演算子の構文で、を使用します。
ms.date: 07/23/2020
f1_keywords:
- bitand_cpp
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: 7e78e4003a31ee59ebd974275df784b7a76e73ce
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229117"
---
# <a name="bitwise-and-operator-amp"></a>ビットごとの AND 演算子:&amp;

## <a name="syntax"></a>構文

> *式* **`&`***式*

## <a name="remarks"></a>解説

ビットごとの AND 演算子 () は、 **`&`** 最初のオペランドの各ビットを2番目のオペランドの対応するビットと比較します。 両方のビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。

ビットごとの AND 演算子へのオペランドは両方とも整数型である必要があります。 [標準変換](standard-conversions.md)で扱う通常の算術変換は、オペランドに適用されます。

## <a name="operator-keyword-for-"></a>& の Operator キーワード

C++ **`bitand`** では、の代替スペルとしてを指定し **`&`** ます。 C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_Bitwise_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise AND
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0xFFFF;      // pattern 1111 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...
}
```

## <a name="see-also"></a>関連項目

[C++ の組み込み演算子、優先順位、および結合規則](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C のビット処理演算子](../c-language/c-bitwise-operators.md)
