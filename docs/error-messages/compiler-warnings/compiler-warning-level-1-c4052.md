---
description: '詳細情報: コンパイラの警告 (レベル 1) C4052'
title: コンパイラの警告 (レベル 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4052
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 0da0823b3268e8f957a87d1c975fb82098fe2511
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160559"
---
# <a name="compiler-warning-level-1-c4052"></a>コンパイラの警告 (レベル 1) C4052

関数に対する宣言の 1 つに可変個の引数が含まれていません。

関数の 1 つの宣言に、可変個の引数が含まれません。 これは無視されます。

次の例では C4052 が生成されます。

```c
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```
