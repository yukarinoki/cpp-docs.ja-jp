---
title: コンパイラの警告 (レベル 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: a07adf37314a11cceb72d6675a66d82f7554bbb6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162063"
---
# <a name="compiler-warning-level-2-c4244"></a>コンパイラの警告 (レベル 2) C4244

' argument ': ' type1 ' から ' type1 ' への変換です。データが失われる可能性があります。

浮動小数点型が整数型に変換されました。  データが失われた可能性があります。

C4244 の場合は、互換性のある型を使用するようにプログラムを変更するか、別のロジックをコードに追加して、変換される値の範囲が使用している型と常に互換性があるようにします。

C4244 は、レベル3、および4でも起動できます。詳細については[、「コンパイラの警告 (レベル3および 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) 」を参照してください。

## <a name="example"></a>例

次の例では C4244 が生成されます。

```cpp
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```
