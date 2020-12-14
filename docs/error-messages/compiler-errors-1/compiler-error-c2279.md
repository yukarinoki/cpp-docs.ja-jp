---
description: 詳細については、「コンパイラエラー C2279」を参照してください。
title: コンパイラ エラー C2279
ms.date: 11/04/2016
f1_keywords:
- C2279
helpviewer_keywords:
- C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
ms.openlocfilehash: e0f8822c77bd243bc2ec6002027d8eadb2aaf8a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228977"
---
# <a name="compiler-error-c2279"></a>コンパイラ エラー C2279

例外指定は typedef 宣言には記述できません

**/Za** では、typedef 宣言では [例外指定](../../cpp/exception-specifications-throw-cpp.md)は許可されません。

次の例では、C2279 が生成されます。

```cpp
// C2279.cpp
// compile with: /Za /c
typedef int (*xy)() throw(...);   // C2279
typedef int (*xyz)();   // OK
```
