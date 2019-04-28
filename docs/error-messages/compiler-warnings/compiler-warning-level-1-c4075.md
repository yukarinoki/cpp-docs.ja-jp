---
title: コンパイラの警告 (レベル 1) C4075
ms.date: 11/04/2016
f1_keywords:
- C4075
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
ms.openlocfilehash: f739e0363cc08d31bd26b063ef13658a392398bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208017"
---
# <a name="compiler-warning-level-1-c4075"></a>コンパイラの警告 (レベル 1) C4075

初期化子が不明な初期化領域にあります。

[#pragma init_seg](../../preprocessor/init-seg.md) が認識できないセクション名を使用しています。 コンパイラはこの **pragma** コマンドを無視します。

次の例では C4075 が生成されます。

```
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```