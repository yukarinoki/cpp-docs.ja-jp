---
description: 詳細については、「コンパイラエラー C3395」を参照してください。
title: コンパイラ エラー C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: 65db71a9dbc076b21d16f3f0c250c20a9b283daa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321970"
---
# <a name="compiler-error-c3395"></a>コンパイラ エラー C3395

' function ': __declspec (dllexport) を、 \_ _clrcall 呼び出し規約を持つ関数に適用することはできません

`__declspec(dllexport)` および [__clrcall](../../cpp/clrcall.md) には互換性がありません。  詳細については、「[dllexport、dllimport](../../cpp/dllexport-dllimport.md)」をご覧ください。

次の例では、C3395 が生成されます。

```cpp
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```
