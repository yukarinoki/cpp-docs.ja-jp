---
title: コンパイラ エラー C2362
ms.date: 11/04/2016
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 17656b2a48a3680a9269d3ca300fd4188eda6b84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364325"
---
# <a name="compiler-error-c2362"></a>コンパイラ エラー C2362

'goto label' で 'identifier' の初期化がスキップされました

コンパイルするときに[/Za](../../build/reference/za-ze-disable-language-extensions.md)識別子が初期化されている防止ラベルにジャンプします。

宣言が入力されていないブロックで囲まれている場合を除き、初期化子と共に宣言ジャンプすることはできませんまたは変数は既に初期化されています。

次の例では C2326 が生成されます。

```
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

考えられる解決方法:

```
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```