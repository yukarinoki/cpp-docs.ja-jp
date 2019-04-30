---
title: コンパイラの警告 (レベル 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 75148c210ddd2a611061d58c036d12c084f442cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400049"
---
# <a name="compiler-warning-level-1-c4020"></a>コンパイラの警告 (レベル 1) C4020

'function': 実引数が多すぎます

関数呼び出しで指定された実引数の数は、関数プロトタイプまたは定義の仮引数の数を超えています。 コンパイラは、関数の呼び出し規約に従って実際の余分なパラメーターを渡します。

次の例では、C4020 が生成されます。

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

考えられる解決方法:

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```