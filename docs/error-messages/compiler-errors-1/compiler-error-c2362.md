---
title: コンパイラ エラー C2362 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f78b850f95614255fed372570742a0f88a9e30e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035982"
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