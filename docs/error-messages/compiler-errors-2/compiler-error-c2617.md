---
description: 詳細については、「コンパイラエラー C2617」を参照してください。
title: コンパイラエラー C2617
ms.date: 11/04/2016
f1_keywords:
- C2617
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
ms.openlocfilehash: 3522b9f07911fb674f95f6ae09193f9bc35567e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338627"
---
# <a name="compiler-error-c2617"></a>コンパイラエラー C2617

' function ': 一致する return ステートメントがありません。

指定された関数には宣言された戻り値の型がありませんが、前の return ステートメントで値が指定されていませんでした。

次の例では、C2617 が生成されます。

```cpp
// C2617.cpp
int i;
func() {   // no return type prototype
   if( i ) return;   // no return value
   else return( 1 );   // C2617 detected on this line
}
```

考えられる解決策:

```cpp
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
