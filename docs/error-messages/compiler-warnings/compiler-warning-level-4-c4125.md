---
title: コンパイラの警告 (レベル 4) C4125 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4125
dev_langs:
- C++
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7042dd8689bf5a9bafc35d6bdaa6028f0c52df2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087241"
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