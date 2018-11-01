---
title: コンパイラの警告 (レベル 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: e0582f3dfdd223b4571e361dc69fae1990aeea1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498216"
---
# <a name="compiler-warning-level-4-c4242"></a>コンパイラの警告 (レベル 4) C4242

'identifier': 'type1' から 'type2'、データ損失の可能性への変換

型が異なるです。 型変換すると、データが失われる可能性があります。 コンパイラで型変換を行います。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

C4242 の詳細については、次を参照してください。[一般的なコンパイラ エラー](/windows/desktop/WinProg64/common-compiler-errors)します。

次の例では、C4242 が生成されます。

```
// C4242.cpp
// compile with: /W4
#pragma warning(4:4242)
int func() {
   return 0;
}

int main() {
   char a;
   a = func();   // C4242, return type and variable type do not match
}
```