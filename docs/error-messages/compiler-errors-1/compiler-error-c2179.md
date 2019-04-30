---
title: コンパイラ エラー C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 4a8abd8d862d4d6b08b1d0efd1d47d0413b60a81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385993"
---
# <a name="compiler-error-c2179"></a>コンパイラ エラー C2179

'type': 属性引数は、型パラメーターを使用できません

ジェネリック型パラメーターは、実行時に解決されます。 ただし、属性のパラメーターは、コンパイル時に解決する必要があります。 そのため、属性の引数としてジェネリック型パラメーターを使用することはできません。

## <a name="example"></a>例

次の例では、C2179 が生成されます。

```
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