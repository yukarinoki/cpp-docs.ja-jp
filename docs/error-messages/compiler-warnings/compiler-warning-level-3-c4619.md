---
description: '詳細情報: コンパイラの警告 (レベル 3) C4619'
title: コンパイラの警告 (レベル 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: c108e4d1a0845cc6629a36307c33fc8342cadd67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337271"
---
# <a name="compiler-warning-level-3-c4619"></a>コンパイラの警告 (レベル 3) C4619

\#プラグマ警告: 警告番号 ' number ' がありません

存在しない警告を無効にしようとしました。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4619 が生成されます。

```cpp
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```
