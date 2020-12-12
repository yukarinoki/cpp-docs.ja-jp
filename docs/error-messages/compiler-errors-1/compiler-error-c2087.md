---
description: 詳細については、「コンパイラエラー C2087」を参照してください。
title: コンパイラエラー C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 98e54a8df8f06230f1adca1cb6d2f23f80acff8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252039"
---
# <a name="compiler-error-c2087"></a>コンパイラエラー C2087

' identifier ': 添字がありません。

複数の添字を持つ配列の定義に、1より大きい次元の添字の値がありません。

次の例では、C2087 が生成されます。

```cpp
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

考えられる解決策:

```cpp
// C2087b.cpp
int main() {
   char b[4][5];
}
```
