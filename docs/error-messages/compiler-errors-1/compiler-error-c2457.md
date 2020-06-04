---
title: コンパイラ エラー C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 40e666b1f2b566ca6309ee7759452647f8101a38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205245"
---
# <a name="compiler-error-c2457"></a>コンパイラ エラー C2457

> '*macro*': 定義済みマクロは関数本体の外側には記述できません

関数などの定義済みマクロ[&#95; &#95;をグローバル空間で使用しようとしまし&#95;](../../preprocessor/predefined-macros.md)た。

## <a name="example"></a>例

次の例では、C2457 を生成し、正しい使用法も示しています。

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```
