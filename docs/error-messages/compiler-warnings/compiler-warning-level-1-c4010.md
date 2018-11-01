---
title: コンパイラの警告 (レベル 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 40c6724daf17c1c0b546bb7bc64bb704f732e8d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441250"
---
# <a name="compiler-warning-level-1-c4010"></a>コンパイラの警告 (レベル 1) C4010

単一行コメントには、行連結文字が含まれています。

導入された単一行のコメント//、円記号が含まれています (\\) 行連結文字として機能します。 コンパイラは、続きとなる次の行を考慮し、コメントとして扱われます。

いくつか構文エディターは、コメントとして連結文字の次の行を示していません。 構文の色分けで、この警告が発生した行を無視します。

次の例では、C4010 が生成されます。

```
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```