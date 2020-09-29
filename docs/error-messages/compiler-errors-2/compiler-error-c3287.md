---
title: コンパイラ エラー C3287
description: Microsoft C++ コンパイラエラー C3287 について説明します。
ms.date: 09/25/2020
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: 4067355ef1bc1992d0f8519656bcd1063179aef4
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414322"
---
# <a name="compiler-error-c3287"></a>コンパイラ エラー C3287

> 型 '*type*' (GetEnumerator の戻り値の型) には、適切なパブリック MoveNext メンバー関数およびパブリック Current プロパティが含まれている必要があります

## <a name="remarks"></a>解説

ユーザー定義のコレクション クラスには、 `MoveNext` と `Current`の定義を含める必要があります。

詳細については、「 [」](../../dotnet/for-each-in.md)の「」を参照してください。

## <a name="example"></a>例

次の例では C3287 が生成されます。

```cpp
// C3287.cpp
// compile with: /clr
using namespace System;

ref struct R {
   bool MoveNext() {
      return true;
   }
   property Object^ Current {
      Object^ get() {
         Object ^ o = gcnew Object;
         return o;
      }
   }
};

ref struct R2 {
   R ^GetEnumerator() {
      R^ r = gcnew R;
      return r;
   }
};

ref struct T {};

ref struct T2 {
   T ^GetEnumerator() {
      T^ t = gcnew T;
      return t;
   }
};

int main() {
   for each (int i in gcnew T2) {}   // C3287
   for each (int i in gcnew R2) {}   // OK
}
```
