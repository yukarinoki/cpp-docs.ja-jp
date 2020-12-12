---
description: 詳細については、「コンパイラエラー C3204」を参照してください。
title: コンパイラ エラー C3204
ms.date: 11/04/2016
f1_keywords:
- C3204
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
ms.openlocfilehash: 8e9275cada58988c9dac3942569fb0416ddff0ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285735"
---
# <a name="compiler-error-c3204"></a>コンパイラ エラー C3204

catch ブロック内から '_alloca' を呼び出すことはできません。

このエラーは、catch ブロック内から [_alloca](../../c-runtime-library/reference/alloca.md) への呼び出しを使用すると発生します。

## <a name="example"></a>例

次の例では C3204 が生成されます。

```cpp
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
