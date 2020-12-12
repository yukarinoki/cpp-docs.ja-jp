---
description: 詳細については、「コンパイラエラー C2479」を参照してください。
title: コンパイラ エラー C2479
ms.date: 11/04/2016
f1_keywords:
- C2479
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
ms.openlocfilehash: 7193112ee546b7314075b105cb88c68fce71a256
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123943"
---
# <a name="compiler-error-c2479"></a>コンパイラ エラー C2479

' identifier ': ' allocate () ' は静的なデータ項目に対してのみ有効です

構文は、 `__declspec( allocate())` 静的なデータに対してのみ使用できます。

次の例では、C2479 が生成されます。

```cpp
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```
