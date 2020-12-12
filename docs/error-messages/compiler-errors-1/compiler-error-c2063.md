---
description: 詳細については、「コンパイラエラー C2063」を参照してください。
title: コンパイラ エラー C2063
ms.date: 11/04/2016
f1_keywords:
- C2063
helpviewer_keywords:
- C2063
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
ms.openlocfilehash: 18b2cd6bf68144245b85d744923404f4a27d63f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328612"
---
# <a name="compiler-error-c2063"></a>コンパイラ エラー C2063

'identifier': 関数ではありません。

識別子が関数として使用されていますが、関数として宣言されていません。

次の例では C2063 エラーが生成されます。

```c
// C2063.c
int main() {
   int i, j;
   j = i();    // C2063, i is not a function
}
```

考えられる解決策:

```c
// C2063b.c
int i() { return 0;}
int main() {
   int j;
   j = i();
}
```
