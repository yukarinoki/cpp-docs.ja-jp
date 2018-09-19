---
title: コンパイラの警告 (レベル 4) C4208 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4208
dev_langs:
- C++
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ee87ad1d43b20c4d0a72b877b05b1ba4c084a1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064623"
---
# <a name="compiler-warning-level-4-c4208"></a>コンパイラの警告 (レベル 4) C4208

使用される標準の拡張機能: delete [exp] - exp を評価が無視されます

Microsoft 拡張機能 (/Ze)、かっこ内の値を使用して、配列を削除することができます、 [delete 演算子](../../cpp/delete-operator-cpp.md)します。 値は無視されます。

```
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

このような値は、ANSI 互換の無効な ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。