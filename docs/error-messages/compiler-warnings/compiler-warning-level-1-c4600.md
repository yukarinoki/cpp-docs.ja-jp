---
title: コンパイラの警告 (レベル 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: 15ad64ad29f6f01253a2329fb04897c299cedff9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186076"
---
# <a name="compiler-warning-level-1-c4600"></a>コンパイラの警告 (レベル 1) C4600

\#プラグマ ' macro name ': 有効な空でない文字列が必要です。

[Pop_macro](../../preprocessor/pop-macro.md)または[push_macro](../../preprocessor/push-macro.md)でマクロ名をプッシュまたはポップするときに、空の文字列を指定することはできません。

次の例では、C4600 が生成されます。

```cpp
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```
