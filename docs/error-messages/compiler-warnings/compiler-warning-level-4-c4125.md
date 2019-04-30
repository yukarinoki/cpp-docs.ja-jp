---
title: コンパイラの警告 (レベル 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 3b82bfd1a1acff07a0fd47bbd2abfb08178a74c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401359"
---
# <a name="compiler-warning-level-4-c4125"></a>コンパイラの警告 (レベル 4) C4125

8 進数のエスケープ シーケンスが、10 進数のところで中断されました。

コンパイラは、10 進数を含まない 8 進数を評価し、10 進数を文字と見なします。

## <a name="example"></a>例

```
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

数字 9 を文字として使用する場合は、次のように例を修正します。

```
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```