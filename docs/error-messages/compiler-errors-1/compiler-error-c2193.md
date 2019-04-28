---
title: コンパイラ エラー C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 1eb1145b7927733ab82253632847da90542250fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302619"
---
# <a name="compiler-error-c2193"></a>コンパイラ エラー C2193

'identifier': 既にセグメント内

関数を使用して 2 つの異なるセグメントに格納された`alloc_text`と`code_seg`プラグマ。

次の例では、C2193 が生成されます。

```
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```