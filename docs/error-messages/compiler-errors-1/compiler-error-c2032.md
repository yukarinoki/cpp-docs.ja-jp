---
title: コンパイラ エラー C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: 5743aba880f23d7706940936fc4a3a1973a84ca1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400514"
---
# <a name="compiler-error-c2032"></a>コンパイラ エラー C2032

'identifier': 関数は 'structorunion' の構造体/共用体のメンバーであることはできません

構造体または共用体が、c 言語ではありませんが、C++ では許可されているメンバー関数エラーを解決するには、C++ プログラムとしてコンパイルするか、メンバー関数を削除します。

次の例では、C2032 が生成されます。

```
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

考えられる解決方法:

```
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```