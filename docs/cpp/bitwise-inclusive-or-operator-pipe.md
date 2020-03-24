---
title: 'ビット処理包括的 OR 演算子: |'
ms.date: 06/14/2018
f1_keywords:
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 38def2b1ac585c751699227d2a065b45145d290d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190756"
---
# <a name="bitwise-inclusive-or-operator-"></a>ビット処理包括的 OR 演算子: |

## <a name="syntax"></a>構文

> *expression1* **|** *expression2*

## <a name="remarks"></a>解説

ビットごとの包括的 OR 演算子 **&#124;** () は、最初のオペランドの各ビットを2番目のオペランドの対応するビットと比較します。 いずれかのビットが 1 の場合、対応する結果ビットは 1 に設定されます。 それ以外の場合、対応する結果ビットは 0 に設定されます。

ビットごとの包括的 OR 演算子のオペランドは両方とも整数型である必要があります。 [標準変換](standard-conversions.md)で扱う通常の算術変換は、オペランドに適用されます。

## <a name="operator-keyword-for-124"></a>の Operator キーワード&#124;

**ビット or**演算子は、に **&#124;** 相当するテキストです。 プログラムの**bitor**演算子にアクセスするには、次の2つの方法があります。ヘッダーファイル \<iso646 > を含めるか、または[/za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張機能を無効にする) コンパイラオプションを使用してコンパイルします。

## <a name="example"></a>例

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>参照

[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C ビット処理演算子](../c-language/c-bitwise-operators.md)
