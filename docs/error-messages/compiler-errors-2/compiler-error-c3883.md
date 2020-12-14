---
description: 詳細については、「コンパイラエラー C3883」を参照してください。
title: コンパイラ エラー C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 216cfdc6385f12ff565eca581068ac5625a09044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274425"
---
# <a name="compiler-error-c3883"></a>コンパイラ エラー C3883

' var ': initonly 静的データメンバーは初期化されなければなりません

[Initonly](../../dotnet/initonly-cpp-cli.md)でマークされた変数が正しく初期化されませんでした。

次の例では、C3883 が生成されます。

```cpp
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

次の例では、考えられる解決策を示しています。

```cpp
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

次の例は、静的コンストラクターでを初期化する方法を示しています。

```cpp
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```
