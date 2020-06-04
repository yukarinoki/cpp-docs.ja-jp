---
title: 'ビットごとの AND 演算子: &amp;'
ms.date: 11/04/2016
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: b5c99d19be3461b10a1126dea3a45d308c0fc558
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181292"
---
# <a name="bitwise-and-operator-amp"></a>ビットごとの AND 演算子: &amp;

## <a name="syntax"></a>構文

```
expression & expression
```

## <a name="remarks"></a>解説

式は、他の and 式、または (以下に言及する型制限に基づき) 等価式、関係式、加算式、乗算式、メンバー式へのポインター、キャスト式、単項式、後置式、または 1 次式である場合もあります。

ビットごとの AND 演算子 ( **&** ) は、最初のオペランドの各ビットを2番目のオペランドの対応するビットと比較します。 両方のビットが 1 の場合、対応する結果ビットは 1 に設定されます。 それ以外の場合、対応する結果ビットは 0 に設定されます。

ビットごとの AND 演算子のオペランドは両方とも整数型である必要があります。 [標準変換](standard-conversions.md)で扱う通常の算術変換は、オペランドに適用されます。

## <a name="operator-keyword-for-"></a>& の Operator キーワード

**Bitand**演算子は **&** に相当するテキストです。 プログラムの**bitand**演算子にアクセスするには、ヘッダーファイル `iso646.h`を含める方法と、 [/za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張機能を無効にする) コンパイラオプションを使用してコンパイルする方法の2つの方法があります。

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

## <a name="see-also"></a>参照

[C++ の組み込み演算子、優先順位と結合規則](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C ビット処理演算子](../c-language/c-bitwise-operators.md)
