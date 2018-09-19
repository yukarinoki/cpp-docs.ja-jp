---
title: コンパイラの警告 (レベル 1) C4052 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4052
dev_langs:
- C++
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67e63f694a190a3d7c694fa99ff0433870a1b9c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103406"
---
# <a name="compiler-warning-level-1-c4052"></a>コンパイラの警告 (レベル 1) C4052

関数に対する宣言の 1 つに可変個の引数が含まれていません。

関数の 1 つの宣言に、可変個の引数が含まれません。 これは無視されます。

次の例では C4052 が生成されます。

```
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```