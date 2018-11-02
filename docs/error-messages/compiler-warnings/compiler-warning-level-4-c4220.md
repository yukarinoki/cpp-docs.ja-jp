---
title: コンパイラの警告 (レベル 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: 177fb01ba4181f72740724d107fe08e6680ed492
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542442"
---
# <a name="compiler-warning-level-4-c4220"></a>コンパイラの警告 (レベル 4) C4220

varargs は残りのパラメーターを一致します。

既定の Microsoft 拡張 (/Ze) では、関数へのポインターと同様が、変数、引数を持つ関数へのポインターを検索します。

## <a name="example"></a>例

```
// C4220.c
// compile with: /W4

int ( *pFunc1) ( int a, ... );
int ( *pFunc2) ( int a, int b);

int main()
{
   if ( pFunc1 != pFunc2 ) {};  // C4220
}
```

ANSI 互換では、このようなポインターが一致しません ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。