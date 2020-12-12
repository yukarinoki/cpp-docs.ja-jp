---
description: '詳細については、「加法演算子: + and-」を参照してください。'
title: '加法演算子: + および -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
ms.openlocfilehash: f87a8682b6f282668c168262cd28230745cb4402
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288374"
---
# <a name="additive-operators--and--"></a>加法演算子: + および -

## <a name="syntax"></a>構文

```
expression + expression
expression - expression
```

## <a name="remarks"></a>解説

加法演算子を次に示します。

- 加算 ( **+** )

- 減算 ( **-** )

これらの二項演算子の結合規則は、左から右方向です。

加法演算子は、数値型またはポインター型のオペランドを受け取ります。 加算 () 演算子の結果は、 **+** オペランドの合計になります。 減算 () 演算子の結果は、 **-** オペランドの差になります。 オペランドの一方または両方がポインターの場合、これらのオペランドは、関数ではなくオブジェクトのポインターである必要があります。 両方のオペランドがポインターの場合、両方とも同じ配列のオブジェクトへのポインターでない限り意味がありません。

加法演算子は、 *算術* 型、 *整数* 型、および *スカラー* 型のオペランドを受け取ります。 次の表にこれらの定義を示します。

### <a name="types-used-with-additive-operators"></a>加法演算子と併用される型

|Type|説明|
|----------|-------------|
|*算術*|整数型および浮動型はまとめて "演算" 型と呼ばれます。|
|*型*|すべてのサイズ (long、short) の char 型と int 型、および列挙型は "整数" 型です。|
|*scalar*|スカラー オペランドは、数値型またはポインター型のオペランドです。|

これらの演算子の有効な組み合わせは以下のとおりです。

*算術*  + *算術*

*スカラー*  + *整数*

*整数*  + *スカラー*

*算術*  - *算術*

*スカラー*  - *スカラー*

加算と減算が同等の操作ではないことに注意してください。

両方のオペランドが算術型の場合、「 [標準変換](standard-conversions.md) 」で説明されている変換がオペランドに適用され、結果は変換後の型になります。

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
> `pIntArray = pIntArray + 1` のような形式のコードは、C++ プログラムではあまり見られません。インクリメントを行う場合は、`pIntArray++` または `pIntArray += 1` のような形式を使用することをお勧めします。

## <a name="pointer-subtraction"></a>ポインターの減算

両方のオペランドがポインターの場合、減算の結果は、オペランド間の (配列要素内の) 差になります。 減算式は、 `ptrdiff_t` (標準のインクルードファイルで定義されている) 型の符号付き整数の結果を生成し \<stddef.h> ます。

それが 2 番目のオペランドである限り、オペランドの 1 つは整数型にできます。 減算の結果は、元のポインターと同じ型です。 減算の値は、(*n*  -  *i*) 番目の配列要素へのポインターです。ここで、 *n* は元のポインターが指す要素で、 *i* は2番目のオペランドの整数値です。

## <a name="see-also"></a>関連項目

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 加法演算子](../c-language/c-additive-operators.md)
