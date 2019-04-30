---
title: コンパイラの警告 (レベル 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: 00647e7dafe18ffad2a059b960ebed0a0f4a5d36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401775"
---
# <a name="compiler-warning-level-3-c4619"></a>コンパイラの警告 (レベル 3) C4619

\#pragma 警告: 警告番号 'number' がありません

存在しない警告を無効にしようとしました。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4619 が生成されます。

```
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```