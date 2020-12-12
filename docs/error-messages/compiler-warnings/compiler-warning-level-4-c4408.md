---
description: '詳細情報: コンパイラの警告 (レベル 4) C4408'
title: コンパイラの警告 (レベル 4) C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 94764cd23c8bf4af757afa7bd8a084f61c5f24a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251480"
---
# <a name="compiler-warning-level-4-c4408"></a>コンパイラの警告 (レベル 4) C4408

anonymousstruct または union はデータメンバーを宣言しませんでした

匿名構造体または匿名共用体には、少なくとも 1 つのデータ メンバーが必要です。

次の例では C4408 が生成されます。

```cpp
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```
