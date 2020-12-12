---
description: '詳細情報: コンパイラの警告 (レベル 2) C4302'
title: コンパイラの警告 (レベル 2) C4302
ms.date: 11/04/2016
f1_keywords:
- C4302
helpviewer_keywords:
- C4302
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
ms.openlocfilehash: 0be91208d62c06882713d6b00358665f518103fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173559"
---
# <a name="compiler-warning-level-2-c4302"></a>コンパイラの警告 (レベル 2) C4302

' conversion ': ' type 1 ' から ' type 2 ' への切り捨て

コンパイラは、より大きな型から小さい型への変換を検出しました。 情報が失われる可能性があります。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4302 が生成されます。

```cpp
// C4302.cpp
// compile with: /W2
#pragma warning(default : 4302)
int main() {
   int i;
   char c = (char) &i;     // C4302
   short s = (short) &i;   // C4302
}
```
