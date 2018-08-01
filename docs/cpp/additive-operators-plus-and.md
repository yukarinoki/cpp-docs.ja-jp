---
title: '加法演算子: +、- |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 313e4602c06c1baf090ed7a66c51b308a3f6f586
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402751"
---
# <a name="additive-operators--and--"></a>加法演算子: + および -
## <a name="syntax"></a>構文  
  
```  
expression + expression   
expression - expression  
```  
  
## <a name="remarks"></a>Remarks  
 加法演算子を次に示します。  
  
-   追加 (**+**)  
  
-   減算 (**-**)  
  
 これらの二項演算子の結合規則は、左から右方向です。  
  
 加法演算子は、数値型またはポインター型のオペランドを受け取ります。 加算の結果 (**+**) 演算子はオペランドの合計になります。 減算の結果 (**-**) 演算子は、オペランド間の差。 オペランドの一方または両方がポインターの場合、これらのオペランドは、関数ではなくオブジェクトのポインターである必要があります。 両方のオペランドがポインターの場合、両方とも同じ配列のオブジェクトへのポインターでない限り意味がありません。  
  
 加法演算子のオペランドを受け取ります*算術*、*整数*、および*スカラー*型。 次の表にこれらの定義を示します。  
  
### <a name="types-used-with-additive-operators"></a>加法演算子と併用される型  
  
|型|説明|  
|----------|-------------|  
|*arithmetic*|整数型および浮動型はまとめて "演算" 型と呼ばれます。|  
|*integral*|すべてのサイズ (long、short) の char 型と int 型、および列挙型は "整数" 型です。|  
|*scalar*|スカラー オペランドは、数値型またはポインター型のオペランドです。|  
  
 これらの演算子の有効な組み合わせは以下のとおりです。  
  
 *算術* + *算術*  
  
 *scalar* + *integral*  
  
 *integral* + *scalar*  
  
 *算術* - *算術*  
  
 *scalar* - *scalar*  
  
 加算と減算が同等の操作ではないことに注意してください。  
  
 両方のオペランドが演算型である場合は、変換、「[標準変換](standard-conversions.md)オペランドに適用され結果は変換後の型のです。  
  
## <a name="example"></a>例  
  
```cpp 
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## <a name="pointer-addition"></a>ポインターの加算  
 加算演算のオペランドの 1 つがオブジェクトの配列へのポインターである場合、もう一方は整数型である必要があります。 結果は、元のポインターと同じ型のポインターで、他の配列要素をポイントします。 この概念を次のコードに示します。  
  
```cpp 
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 整数値 1 が `pIntArray` に追加されますが、これは "アドレスに 1 を追加する" ことを意味しません。そうではなく、2 バイト (または `sizeof( int )`) 移動するように、"配列内の次のオブジェクトを指すようにポインターを調整する" ことを意味します。  
  
> [!NOTE]
>  `pIntArray = pIntArray + 1` のような形式のコードは、C++ プログラムではあまり見られません。インクリメントを行う場合は、`pIntArray++` または `pIntArray += 1` のような形式を使用することをお勧めします。  
  
## <a name="pointer-subtraction"></a>ポインターの減算  
 両方のオペランドがポインターの場合、減算の結果は、オペランド間の (配列要素内の) 差になります。 減算式には、符号付き整数型の結果が得られます`ptrdiff_t`(標準インクルード ファイルで定義されている\<stddef.h >)。  
  
 それが 2 番目のオペランドである限り、オペランドの 1 つは整数型にできます。 減算の結果は、元のポインターと同じ型です。 減算の値はへのポインター、(*n* - *は*) 番目の配列要素、 *n*要素を指しています、元のポインターと*は*2 番目のオペランドの整数値です。  
  
## <a name="see-also"></a>関連項目  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 加法演算子](../c-language/c-additive-operators.md)