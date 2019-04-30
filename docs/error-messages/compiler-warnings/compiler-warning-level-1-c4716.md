---
title: コンパイラの警告 (レベル 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 5ec0aea543053d699db7483df7dd7ea91b3af715
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363818"
---
# <a name="compiler-warning-level-1-c4716"></a>コンパイラの警告 (レベル 1) C4716

'function': 値を返さなければいけません

指定された関数では、値は返されませんでした。

関数は void の戻り値の型に対してのみ機能は、戻り値なしの戻り値のコマンドを使用します。

未定義の値が、この関数が呼び出されたときに返されます。

この警告は、自動的にエラーになります。 この動作を変更する場合を使用して、 [#pragma warning](../../preprocessor/warning.md)します。

次の例では、C4716 が生成されます。

```
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```