---
title: コンパイラの警告 (レベル 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: fcfefd5b858df653551e7f3061a41d168c8ff3f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489610"
---
# <a name="compiler-warning-level-1-c4600"></a>コンパイラの警告 (レベル 1) C4600

\#プラグマ 'macro name': 無効な空でない文字列が必要です

プッシュまたはいずれかで、マクロ名を表示するときに、空の文字列を指定することはできません、 [pop_macro](../../preprocessor/pop-macro.md)または[push_macro](../../preprocessor/push-macro.md)します。

次の例では、C4600 が生成されます。

```
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```