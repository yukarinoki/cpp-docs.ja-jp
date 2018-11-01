---
title: '方法: ボックス化を解除する'
ms.date: 11/04/2016
helpviewer_keywords:
- unboxing
ms.assetid: 75794696-9275-47bf-9a7d-5abe6585ab91
ms.openlocfilehash: b2919ecce254a81d6a140fc7906d28646b50ab8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618531"
---
# <a name="how-to-unbox"></a>方法: ボックス化を解除する

ボックス化解除し、値を変更する方法を示します。

## <a name="example"></a>例

```
// vcmcppv2_unboxing.cpp
// compile with: /clr
using namespace System;

int main() {
   int ^ i = gcnew int(13);
   int j;
   Console::WriteLine(*i);   // unboxing
   *i = 14;   // unboxing and assignment
   Console::WriteLine(*i);
   j = safe_cast<int>(i);   // unboxing and assignment
   Console::WriteLine(j);
}
```

```Output
13
14
14
```

## <a name="see-also"></a>関連項目

[ボックス化](../windows/boxing-cpp-component-extensions.md)