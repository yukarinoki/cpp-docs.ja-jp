---
title: コンパイラの警告 (レベル 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a3ce4c81a86920baddfc1b277df0236a96254be4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207397"
---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258

'variable': 定義から、ループは無視されます。外側のスコープから定義を使用すると"

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)と[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)で定義された変数を[の](../../cpp/for-statement-cpp.md)ループが後にスコープ外に移動して、**の**ループが終了します。 この警告は、外側のループ内で定義された、ループ変数と同じ名前の変数は、スコープを含むでもう一度使用する場合に発生します。、**の**ループします。 例:

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