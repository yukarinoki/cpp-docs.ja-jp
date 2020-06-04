---
title: '後置インクリメント演算子と後置デクリメント演算子: ++ および --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
ms.openlocfilehash: 44b1031376abd6c50c3b9706089042995994e495
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177678"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>後置インクリメント演算子と後置デクリメント演算子: ++ および --

## <a name="syntax"></a>構文

```
postfix-expression ++
postfix-expression --
```

## <a name="remarks"></a>解説

C++ には、前置および後置のインクリメント演算子およびデクリメント演算子が用意されています。このセクションでは、後置インクリメント演算子および後置デクリメント演算子についてのみ説明します (詳細については、「[前置インクリメント演算子とデクリメント演算子](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)」を参照してください)。2つの違いは、後置表記法では、後*置式*の後に演算子が表示されます。一方、前置表記法では、演算子は expression の前に記述され*ます。* 次の例は、後置インクリメント演算子を示しています。

```cpp
i++;
```

後置インクリメント演算子 ( **++** ) を適用した場合の効果は、オペランドの値が適切な型の1単位に増加することです。 同様に、後置デクリメント演算子 ( **--** ) を適用する効果は、オペランドの値が適切な型の1単位分減少することです。

後置インクリメントまたはデクリメント式は、各演算子の適用*前*に式の値に評価されることに注意してください。 インクリメントまたはデクリメント操作は、オペランドが評価され*た後*に発生します。 この問題は、後置インクリメントまたはデクリメント演算が、より大きな式のコンテキストで行われる場合にのみ発生します。

後置演算子を関数の引数に適用した場合、引数の値が関数に渡される前にインクリメントまたはデクリメントされる保証はありません。  詳細については、C++ 標準のセクション 1.9.17 を参照してください。

**Long**型のオブジェクトの配列へのポインターに後置インクリメント演算子を適用すると、実際には、ポインターの内部表現に4が加算されます。 この動作により、以前は配列の*n*番目の要素を参照するポインターが、(*n*+ 1) th 要素を参照するようになります。

後置インクリメント演算子と後置デクリメント演算子のオペランドは、算術型またはポインター型の変更可能な ( **const**ではなく) 左辺値である必要があります。 結果の型は、*後置式*の型と同じですが、左辺値ではなくなりました。

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): 後置インクリメント演算子またはデクリメント演算子のオペランドを**bool**型にすることはできません。

次のコードは、後置インクリメント演算子を示しています。

```cpp
// expre_Postfix_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
   int i = 10;
   cout << i++ << endl;
   cout << i << endl;
}
```

列挙型に対する後置インクリメント演算および後置デクリメント演算はサポートされていません。

```cpp
enum Compass { North, South, East, West );
Compass myCompass;
for( myCompass = North; myCompass != West; myCompass++ ) // Error
```

## <a name="see-also"></a>参照

[後置式](../cpp/postfix-expressions.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 後置インクリメント演算子と後置デクリメント演算子](../c-language/c-postfix-increment-and-decrement-operators.md)
