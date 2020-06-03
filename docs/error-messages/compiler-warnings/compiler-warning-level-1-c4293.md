---
title: コンパイラの警告 (レベル 1) C4293
ms.date: 11/04/2016
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 6f224996904c583001496e04c020de97bc932738
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175689"
---
# <a name="compiler-warning-level-1-c4293"></a>コンパイラの警告 (レベル 1) C4293

' operator ': シフト数が負であるか、大きすぎます。未定義の動作です

シフト数が負の値または大きすぎる場合、結果のイメージの動作は未定義になります。

## <a name="example"></a>例

次の例では、C4293 が生成されます。

```cpp
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi) {

   return (hi << 32) | lo;   // C4293

   // try the following line instead
   // return ( (unsigned __int64)hi << 32) | lo;
}
```
