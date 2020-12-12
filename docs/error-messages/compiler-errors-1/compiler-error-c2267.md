---
description: 詳細については、「コンパイラエラー C2267」を参照してください。
title: コンパイラ エラー C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: df69073cbb1956033cf7d028c56e13018e4bbcf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328402"
---
# <a name="compiler-error-c2267"></a>コンパイラ エラー C2267

' function ': ブロックスコープを持つ静的関数は無効です

ローカル関数が宣言されて **`static`** います。 静的関数にはグローバルスコープが必要です。

次の例では、C2267 が生成されます。

```cpp
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```
