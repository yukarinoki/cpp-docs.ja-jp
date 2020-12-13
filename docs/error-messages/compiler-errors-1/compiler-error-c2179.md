---
description: 詳細については、「コンパイラエラー C2179」を参照してください。
title: コンパイラ エラー C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 17ddc839161f36efc668bb52504e2434ec82f995
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335218"
---
# <a name="compiler-error-c2179"></a>コンパイラ エラー C2179

' type ': 属性引数は型パラメーターを使用できません

ジェネリック型パラメーターは、実行時に解決されます。 ただし、属性パラメーターはコンパイル時に解決する必要があります。 したがって、ジェネリック型パラメーターを属性の引数として使用することはできません。

## <a name="example"></a>例

次の例では、C2179 が生成されます。

```cpp
// C2179.cpp
// compile with: /clr
using namespace System;

public ref struct Attr : Attribute {
   Attr(Type ^ a) {
      x = a;
   }

   Type ^ x;
};

ref struct G {};

generic<typename T>
public ref class Z {
public:
   Type ^ d;
   [Attr(T::typeid)]   // C2179
   // try the following line instead
   // [Attr(G::typeid)]
   T t;
};
```
