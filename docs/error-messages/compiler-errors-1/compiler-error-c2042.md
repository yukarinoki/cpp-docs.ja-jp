---
description: 詳細については、「コンパイラエラー C2042」を参照してください。
title: コンパイラ エラー C2042
ms.date: 11/04/2016
f1_keywords:
- C2042
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
ms.openlocfilehash: 3dd4ae7471997e518c854d570b4a2e3aa4ec3856
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175210"
---
# <a name="compiler-error-c2042"></a>コンパイラ エラー C2042

'signed' と 'unsigned' が 1 つの宣言内で同時に使われています。

キーワード **`signed`** と **`unsigned`** は、1つの宣言で使用されます。

次の例では C2042 エラーが生成されます。

```cpp
// C2042.cpp
unsigned signed int i;   // C2042
```

考えられる解決策:

```cpp
// C2042b.cpp
// compile with: /c
unsigned int i;
signed int ii;
```
