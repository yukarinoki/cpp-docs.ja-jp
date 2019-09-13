---
title: コンパイラエラー C2093
ms.date: 11/04/2016
f1_keywords:
- C2093
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
ms.openlocfilehash: d57b452e63f7bf76051ef6a23c5f8f6ba81aed1e
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741152"
---
# <a name="compiler-error-c2093"></a>コンパイラエラー C2093

' variable1 ': 自動変数 ' 変数 2 ' のアドレスを使用して初期化することはできません

[/Za](../../build/reference/za-ze-disable-language-extensions.md)を使用してコンパイルすると、プログラムは自動変数のアドレスを初期化子として使用しようとしました。

次の例では、C2093 が生成されます。

```
// C2093.c
// compile with: /Za /c
void func() {
   int li;   // an implicit auto variable
   int * s[]= { &li };   // C2093 address is not a constant

   // OK
   static int li2;
   int * s2[]= { &li2 };
}
```