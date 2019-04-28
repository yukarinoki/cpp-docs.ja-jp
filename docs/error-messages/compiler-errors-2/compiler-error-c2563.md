---
title: コンパイラ エラー C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 04a10c82fa6aa39bcf1098d6d4aabfc2f769e7c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257856"
---
# <a name="compiler-error-c2563"></a>コンパイラ エラー C2563

仮パラメーター リストが一致しません

関数 (または関数へのポインター) の仮パラメーター リストには、別の関数 (またはメンバー関数へのポインター) のものと一致しません。 結果として、または関数ポインターの割り当ては行われたことはできません。

次の例では、C2563 が生成されます。

```
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```