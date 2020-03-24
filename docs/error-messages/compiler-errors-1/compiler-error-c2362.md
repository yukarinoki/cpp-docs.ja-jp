---
title: コンパイラ エラー C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 330932f53627f8ba09e9e089cec7809eeeb6ab1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206077"
---
# <a name="compiler-error-c2362"></a>コンパイラ エラー C2362

> '*identifier*' の初期化が ' goto *label*' によってスキップされました

[/Za](../../build/reference/za-ze-disable-language-extensions.md)を使用してコンパイルした場合、ラベルへのジャンプによって識別子が初期化されないようにします。

宣言が入力されていないブロックで囲まれている場合、または変数が既に初期化されている場合は、初期化子を持つ宣言の後にのみジャンプできます。

次の例では、C2362 が生成されます。

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

考えられる解決方法:

```cpp
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
