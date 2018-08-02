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
ms.openlocfilehash: 953c03f7c8125713afddd3b3567615be585fc9db
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463149"
---
# <a name="references-c"></a>参照 (C++)
参照は、ポインターと同じように、メモリ内の他の場所に位置するオブジェクトのアドレスを格納します。 参照は、ポインターとは異なり、初期化された後で別のオブジェクトを参照するように指定したり、null に設定したりすることはできません。 参照の 2 種類があります。 左辺値参照を参照している名前付き変数および右辺値参照を参照している、[一時オブジェクト](../cpp/temporary-objects.md)します。 & 演算子は左辺値参照を示し、&& 演算子は、コンテキストによって右辺値参照またはユニバーサル参照 (右辺値または左辺値) を示します。  
  
 参照は次の構文を使用して宣言できます。  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 参照を指定する任意の有効な宣言子を使用できます。 参照が関数または配列型への参照でない限り、次の簡略化された構文が適用されます。  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 参照は次の順序で宣言します。  
  
 1. 宣言指定子:  
  
-   ストレージ クラスの指定子 (省略可能)。  
  
-   省略可能な**const**や**揮発性**修飾子。  
  
-   型指定子: 型の名前。  
  
-   2. 宣言子:   
  
-   オプションの Microsoft 固有の修飾子。 詳細については、次を参照してください。 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)します。  
  
-   & 演算子または && 演算子。  
  
-   省略可能な**const**や**揮発性**修飾子。  
  
-   識別子。  
  
 3. 初期化子 (省略可能)。  
  
 複雑な宣言子フォーム参照の配列および関数へのポインターは、配列と関数への参照にも適用[ポインター](../cpp/pointers-cpp.md)します。  
  
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
  
 次のプログラムでは、オブジェクトの名前 `Today` とオブジェクトへの参照 `TodayRef` を、プログラム内で同じように使用できることに注意してください。  
  
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
 [参照型関数の引数](../cpp/reference-type-function-arguments.md)  
 [参照型関数の戻り値](../cpp/reference-type-function-returns.md)  
 [ポインターへの参照](../cpp/references-to-pointers.md)  
  
