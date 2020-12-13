---
description: 詳細については、「コンパイラエラー C2032」を参照してください。
title: コンパイラエラー C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: cb39a539dc1e360f70cc2b217d50f3a1eabcf0f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175457"
---
# <a name="compiler-error-c2032"></a>コンパイラエラー C2032

' identifier ': 関数を構造体/共用体 ' structorunion ' のメンバーにすることはできません

構造体または共用体にメンバー関数がありますが、C++ では使用できますが、C では許可されていません。このエラーを解決するには、C++ プログラムとしてコンパイルするか、メンバー関数を削除します。

次の例では、C2032 が生成されます。

```c
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

考えられる解決策:

```c
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
