---
description: 詳細については、「コンパイラエラー C2054」を参照してください。
title: コンパイラエラー C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: b86c805a5687679cfa4bb5ed667c3bcf3adbad94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341361"
---
# <a name="compiler-error-c2054"></a>コンパイラエラー C2054

' identifier ' の後に ' (' が必要です

関数識別子は、末尾にかっこが必要なコンテキストで使用されます。

このエラーは、複雑な初期化で等号 (=) を省略することによって発生することがあります。

次の例では、C2054 が生成されます。

```c
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

考えられる解決策:

```c
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```
