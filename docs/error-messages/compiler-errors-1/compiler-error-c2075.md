---
title: コンパイラ エラー C2075
ms.date: 11/04/2016
f1_keywords:
- C2075
helpviewer_keywords:
- C2075
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
ms.openlocfilehash: d53ef6f34b061a04f2c136b4e349d4951529b94b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303178"
---
# <a name="compiler-error-c2075"></a>コンパイラ エラー C2075

'identifier' : 配列の初期化には中かっこ ({}) が必要です

指定した配列初期化子の周囲に中かっこがありませんでした。

次の例では C2075 エラーが生成されます。

```
// C2075.c
int main() {
   int i[] = 1, 2, 3 };   // C2075
}
```

考えられる解決方法:

```
// C2075b.c
int main() {
   int j[] = { 1, 2, 3 };
}
```