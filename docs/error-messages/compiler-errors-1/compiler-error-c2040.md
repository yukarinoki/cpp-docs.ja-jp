---
title: コンパイラ エラー C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: b45ec25f1ed516ae73b242fdcc7c66f68c92f724
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387111"
---
# <a name="compiler-error-c2040"></a>コンパイラ エラー C2040

'operator' : 間接参照のレベルが 'identifier1' と 'identifier2' で異なっています。

指定したオペランドを含む式に、互換性がないオペランド型または暗黙的に変換されるオペランド型が含まれています。 オペランドが両方とも数値型である場合や、両方とも数値型でない場合 (つまり配列やポインターの場合)、オペランドは変更されずに使用されます。 片方が数値型であるのにもう片方が数値型でない場合、数値型の方は数値型でない方の型に変換されます。

この例では C2040 が生成され、その修正方法が示されています。

```
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```