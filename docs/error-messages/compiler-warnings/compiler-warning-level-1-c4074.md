---
title: コンパイラの警告 (レベル 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: 7a11112962872788df855bfc63b869193188fab9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164080"
---
# <a name="compiler-warning-level-1-c4074"></a>コンパイラの警告 (レベル 1) C4074

初期化子がコンパイラの予約された初期化領域に配置されました

[#Pragma init_seg](../../preprocessor/init-seg.md)によって指定されるコンパイラの初期化領域は、Microsoft によって予約されています。 この領域のコードは、C ランタイムライブラリを初期化する前に実行できます。

次の例では、C4074 が生成されます。

```cpp
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```
