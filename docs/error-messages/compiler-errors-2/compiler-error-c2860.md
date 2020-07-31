---
title: コンパイラ エラー C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 25ae5f0ffee659dee2e0ac388da207a5165ecc8e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214569"
---
# <a name="compiler-error-c2860"></a>コンパイラ エラー C2860

' (void) ' を除き、' void ' を引数型にすることはできません

型を **`void`** 他の引数と共に引数の型として使用することはできません。

次の例では、C2860 が生成されます。

```cpp
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```
