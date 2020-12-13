---
description: 詳細については、「コンパイラエラー C2193」を参照してください。
title: コンパイラ エラー C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 63fc345e2898c3fe2bf222bf83ce0d703be97972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337655"
---
# <a name="compiler-error-c2193"></a>コンパイラ エラー C2193

' identifier ': 既にセグメントに含まれています

`alloc_text`とプラグマを使用して、関数が2つの異なるセグメントに配置されました `code_seg` 。

次の例では、C2193 が生成されます。

```cpp
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```
