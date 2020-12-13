---
description: 詳細については、「コンパイラエラー C2457」を参照してください。
title: コンパイラ エラー C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 1fea5192b97e280a38f674a67b0bf739041ffe97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332370"
---
# <a name="compiler-error-c2457"></a>コンパイラ エラー C2457

> '*macro*': 定義済みマクロは関数本体の外側には記述できません

グローバル空間で [&#95;&#95;関数&#95;&#95;](../../preprocessor/predefined-macros.md)などの定義済みマクロを使用しようとしました。

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
