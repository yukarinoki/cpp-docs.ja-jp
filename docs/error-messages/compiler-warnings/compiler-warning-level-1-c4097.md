---
title: コンパイラの警告 (レベル 1) C4097
ms.date: 11/04/2016
f1_keywords:
- C4097
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
ms.openlocfilehash: d27e1d33db7a531d541bffdac015176de72077d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152199"
---
# <a name="compiler-warning-level-1-c4097"></a>コンパイラの警告 (レベル 1) C4097

プラグマ パラメーターに 'restore' または 'off' が必要です。

プラグマに無効な値が渡されました。

次の例では C4097 が生成されます。

```
// C4097.cpp
// compile with: /W1
#pragma runtime_checks("",test)   // C4097
// try the following line instead
// #pragma runtime_checks("",off)

int main() {
}
```