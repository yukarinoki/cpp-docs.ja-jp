---
title: コンパイラ エラー C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: d1ba3a0f975dbc96c9c6ca51a8dac89b5a614572
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439483"
---
# <a name="compiler-error-c2344"></a>コンパイラ エラー C2344

align(#): アラインメントは 2 の累乗でなければなりません

[align](../../cpp/align-cpp.md) キーワードを使用する場合は、渡す値は 2 の累乗である必要があります。

たとえば、3 は 2 の累乗ではないため、次のコードでは C2344 が生成されます。

```
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```