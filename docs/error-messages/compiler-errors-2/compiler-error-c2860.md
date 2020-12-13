---
description: 詳細については、「コンパイラエラー C2860」を参照してください。
title: コンパイラ エラー C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 27474577e31cdc046769f9fc26686d3aaa7f3e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341166"
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
