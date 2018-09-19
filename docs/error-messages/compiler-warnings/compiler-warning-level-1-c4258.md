---
title: コンパイラの警告 (レベル 1) C4258 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4d9aacd6e3681a1eb42073df8a13d7ce72c5634
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083536"
---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258

'variable': 定義から、ループは無視されます。外側のスコープから定義を使用すると"

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)と[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)で定義された変数を[の](../../cpp/for-statement-cpp.md)ループが後にスコープ外に移動して、**の**ループが終了します。 この警告は、外側のループ内で定義された、ループ変数と同じ名前の変数は、スコープを含むでもう一度使用する場合に発生します。、**の**ループします。 例えば:

```
// C4258.cpp
// compile with: /Zc:forScope /W1
int main()
{
   int i;
   {
      for (int i =0; i < 1; i++)
         ;
      i = 20;   // C4258 i (in for loop) has gone out of scope
   }
}
```