---
title: コンパイラの警告 (レベル 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: d9b0259e95198396d8c34ca43781045248e22ad9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374743"
---
# <a name="compiler-warning-level-1-c4074"></a>コンパイラの警告 (レベル 1) C4074

初期化子がコンパイラの予約初期化領域

指定されているコンパイラ初期化領域[#pragma init_seg](../../preprocessor/init-seg.md)、Microsoft によって予約されています。 この領域のコードは、C ランタイム ライブラリの初期化の前に実行できます。

次の例では、C4074 が生成されます。

```
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```