---
title: コンパイラの警告 (レベル 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: 11c6b1ad50c44ac4ad2a9d014e57efef097d9d8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401178"
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