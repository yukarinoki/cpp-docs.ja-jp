---
title: 参照 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3a93d434907a2a3ff13053ee4b932201de22f3a
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861409"
---
# <a name="references-c"></a>参照 (C++)

参照は、ポインターと同じように、メモリ内の他の場所に位置するオブジェクトのアドレスを格納します。 参照は、ポインターとは異なり、初期化された後で別のオブジェクトを参照するように指定したり、null に設定したりすることはできません。 参照の 2 種類があります。 左辺値参照を参照している名前付き変数および右辺値参照を参照している、[一時オブジェクト](../cpp/temporary-objects.md)します。 & 演算子は左辺値参照を示し、&& 演算子は、コンテキストによって右辺値参照またはユニバーサル参照 (右辺値または左辺値) を示します。

参照は次の構文を使用して宣言できます。

> \[*ストレージ クラス指定子*] \[ *cv 修飾子*]*型指定子* \[ *ms 修飾子*] *宣言子* \[ **=** *式*]**;**

参照を指定する任意の有効な宣言子を使用できます。 参照が関数または配列型への参照でない限り、次の簡略化された構文が適用されます。

> \[*ストレージ クラス指定子*] \[ *cv 修飾子*]*型指定子* \[ **&** または**&&**] \[ *cv 修飾子*]*識別子* \[ **=** *式*]**;**

参照は次の順序で宣言します。

1. 宣言指定子:

   - ストレージ クラスの指定子 (省略可能)。

   - 省略可能な**const**や**揮発性**修飾子。

   - 型指定子: 型の名前。

1. 宣言子: 

   - オプションの Microsoft 固有の修飾子。 詳細については、次を参照してください。 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)します。

   - **&** 演算子または**&&** 演算子。

   - 省略可能な**const**や**揮発性**修飾子。

   - 識別子。

1. 初期化子 (省略可能)。

複雑な宣言子の形式の配列および関数へのポインターは配列および関数への参照にも適用されます。 詳細については、次を参照してください。[ポインター](../cpp/pointers-cpp.md)します。

1 つの宣言指定子の後のコンマ区切りリストに、複数の宣言子と初期化子を含めることができます。 例えば:

```cpp
int &i;
int &i, &j;
```

次のように、参照、ポインター、およびオブジェクトをまとめて宣言できます。

```cpp
int &ref, *ptr, k;
```

参照は、オブジェクトのアドレスを保持しますが、構文的にはオブジェクトと同様に動作します。

次のプログラムでは、オブジェクトの名前 `s` とオブジェクトへの参照 `SRef` を、プログラム内で同じように使用できることに注意してください。

## <a name="example"></a>例

```cpp
// references.cpp
#include <stdio.h>
struct S {
   short i;
};

int main() {
   S  s;   // Declare the object.
   S& SRef = s;   // Declare the reference.
   s.i = 3;

   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);

   SRef.i = 4;
   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);
}
```

```Output
3
3
4
4
```

## <a name="see-also"></a>関連項目

[参照型関数の引数](../cpp/reference-type-function-arguments.md)<br/>
[参照型関数の戻り値](../cpp/reference-type-function-returns.md)<br/>
[ポインターへの参照](../cpp/references-to-pointers.md)
