---
title: コンパイラ エラー C2457 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2457
dev_langs:
- C++
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61cdb4f4b679bab858717a6fb96838f389822a6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2457"></a>コンパイラ エラー C2457

> '*マクロ*': 定義済みマクロは関数本体の外部で表示できません。

など、定義済みマクロを使用しようとしています。 [ &#95;&#95;関数&#95;&#95;](../../preprocessor/predefined-macros.md)、グローバル空間内です。

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