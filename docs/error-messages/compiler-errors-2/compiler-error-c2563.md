---
title: コンパイラ エラー C2563 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eec8526df1c5ff69899dd0a2d103cb5f28d4c00c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067404"
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