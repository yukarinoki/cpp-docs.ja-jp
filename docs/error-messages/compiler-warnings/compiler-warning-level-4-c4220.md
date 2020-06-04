---
title: コンパイラの警告 (レベル 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: 90b66a9d819d3014c1e1437b691766ade420bd4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161257"
---
# <a name="compiler-warning-level-4-c4220"></a>コンパイラの警告 (レベル 4) C4220

varargs は残りのパラメーターと一致します

既定の Microsoft 拡張機能 (/Ze) では、関数へのポインターは、類似した、変数、引数を持つ関数へのポインターと一致します。

## <a name="example"></a>例

```c
// C4220.c
// compile with: /W4

int ( *pFunc1) ( int a, ... );
int ( *pFunc2) ( int a, int b);

int main()
{
   if ( pFunc1 != pFunc2 ) {};  // C4220
}
```

このようなポインターは ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では一致しません。
