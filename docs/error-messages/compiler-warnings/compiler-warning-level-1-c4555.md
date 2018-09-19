---
title: コンパイラの警告 (レベル 1) C4555 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4555
dev_langs:
- C++
helpviewer_keywords:
- C4555
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99adbc75bc6663e9f30950866a0c258be6e10164
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097264"
---
# <a name="compiler-warning-level-1-c4555"></a>コンパイラの警告 (レベル 1) C4555

式の影響はありません; 式の副作用が必要です。

この警告は、式効果がない場合を通知します。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

例えば:

```
// C4555.cpp
// compile with: /W1
#pragma warning(default:4555)

void func1()
{
   1;   // C4555
}

void func2()
{
   int x;
   x;   // C4555
}

int main()
{
}
```