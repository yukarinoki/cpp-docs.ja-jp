---
title: 'ビット処理排他的 OR 演算子: ^'
description: C++ 標準言語の排他または演算子の構文で、を使用します。
ms.date: 07/23/2020
f1_keywords:
- xor_cpp
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 0f64b9f90b70756d29fcabb361cc07abe58e0a54
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229104"
---
# <a name="bitwise-exclusive-or-operator-"></a>ビット処理排他的 OR 演算子: ^

## <a name="syntax"></a>構文

> *式* **`^`***式*

## <a name="remarks"></a>解説

ビットごとの排他的 OR 演算子 () は、 **`^`** 最初のオペランドの各ビットを2番目のオペランドの対応するビットと比較します。 1番目のオペランドのビットが0でもう一方のビットが1の場合、対応する結果ビットは1に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。

演算子へのオペランドは両方とも整数型である必要があります。 [標準変換](standard-conversions.md)で扱う通常の算術変換は、オペランドに適用されます。

## <a name="operator-keyword-for-"></a>^ の Operator キーワード

C++ **`xor`** では、の代替スペルとしてを指定し **`^`** ます。 C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。


## <a name="example"></a>例

```cpp
// expre_Bitwise_Exclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise exclusive OR
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xFFFF;      // pattern 1111 ...

   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...
}
```

## <a name="see-also"></a>関連項目

[C++ の組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
