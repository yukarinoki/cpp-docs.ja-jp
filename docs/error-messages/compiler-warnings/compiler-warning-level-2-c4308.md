---
description: '詳細情報: コンパイラの警告 (レベル 2) C4308'
title: コンパイラの警告 (レベル 2) C4308
ms.date: 11/04/2016
f1_keywords:
- C4308
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
ms.openlocfilehash: 180372bef17180b74431ea3c317417f15a6a231d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339190"
---
# <a name="compiler-warning-level-2-c4308"></a>コンパイラの警告 (レベル 2) C4308

符号なしの型に変換された負の整数定数

式は、負の整数定数を符号なしの型に変換します。 式の結果は、意味がない可能性があります。

## <a name="example"></a>例

```cpp
// C4308.cpp
// compile with: /W2
unsigned int u = (-5 + 3U);   // C4308

int main()
{
}
```
