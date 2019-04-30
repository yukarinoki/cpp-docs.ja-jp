---
title: コンパイラの警告 (レベル 4) C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 3c7613d42bbd0ac7fa58a0b95ba68efb60d9f50a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391570"
---
# <a name="compiler-warning-level-4-c4408"></a>コンパイラの警告 (レベル 4) C4408

anonymousstruct または共用体の宣言がありません、データ メンバー

匿名構造体または匿名共用体には、少なくとも 1 つのデータ メンバーが必要です。

次の例では C4408 が生成されます。

```
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```