---
title: コンパイラ エラー C2617
ms.date: 11/04/2016
f1_keywords:
- C2617
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
ms.openlocfilehash: 21add86e37d32525b69a02e848444919fe2a79f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208519"
---
# <a name="compiler-error-c2617"></a>コンパイラ エラー C2617

'function': 矛盾の return ステートメント

指定した関数には、宣言された戻り値の型、直前の return ステートメントでは、値が指定されていませんがありません。

次の例では、C2617 が生成されます。

```
// C2617.cpp
int i;
func() {   // no return type prototype
   if( i ) return;   // no return value
   else return( 1 );   // C2617 detected on this line
}
```

考えられる解決方法:

```
// C2617b.cpp
// compile with: /c
int i;
int MyF() {
   if (i)
      return 0;
   else
      return (1);
}
```