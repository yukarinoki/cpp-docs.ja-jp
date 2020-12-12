---
description: '詳細情報: コンパイラの警告 (レベル 3) C4646'
title: コンパイラの警告 (レベル 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: 045c5d4557a50824235833528f8b46ff77b683e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301829"
---
# <a name="compiler-warning-level-3-c4646"></a>コンパイラの警告 (レベル 3) C4646

__declspec(noreturn) で宣言された関数に、non-void 戻り値の型があります。

[Noreturn](../../cpp/noreturn.md)修飾子でマークされた関数の **`__declspec`** 戻り値の型は [void](../../cpp/void-cpp.md)である必要があります。

次の例では C4646 が生成されます。

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```
