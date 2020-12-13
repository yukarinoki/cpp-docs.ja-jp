---
description: '詳細情報: コンパイラの警告 (レベル 4) C4400'
title: コンパイラの警告 (レベル 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: c91a77758127b5c5b5c5ab742c980f6367830812
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136241"
---
# <a name="compiler-warning-level-4-c4400"></a>コンパイラの警告 (レベル 4) C4400

' type ': この型の const/volatile 修飾子はサポートされていません

[Const](../../cpp/const-cpp.md)修飾子と[volatile](../../cpp/volatile-cpp.md)修飾子は、共通言語ランタイム型の変数では使用できません。

## <a name="example"></a>例

次の例では、C4400 が生成されます。

```cpp
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```
