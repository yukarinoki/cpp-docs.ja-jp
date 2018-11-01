---
title: コンパイラ エラー C3204
ms.date: 11/04/2016
f1_keywords:
- C3204
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
ms.openlocfilehash: 4c34ad35916f01323a72102c7099d4afd0ab17be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539296"
---
# <a name="compiler-error-c3204"></a>コンパイラ エラー C3204

catch ブロック内から '_alloca' を呼び出すことはできません。

このエラーは、catch ブロック内から [_alloca](../../c-runtime-library/reference/alloca.md) への呼び出しを使用すると発生します。

## <a name="example"></a>例

次の例では C3204 が生成されます。

```
// C3204.cpp
// compile with: /EHsc
#include <malloc.h>

void ShowError(void)
{
   try
   {
   }
   catch(...)
   {
      _alloca(1);   // C3204
   }
}
```