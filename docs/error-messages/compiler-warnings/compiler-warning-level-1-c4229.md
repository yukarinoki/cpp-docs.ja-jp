---
title: コンパイラの警告 (レベル 1) C4229
ms.date: 11/04/2016
f1_keywords:
- C4229
helpviewer_keywords:
- C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
ms.openlocfilehash: 05d11a02d3aea8748a2955dff77a0af750ee0275
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575540"
---
# <a name="compiler-warning-level-1-c4229"></a>コンパイラの警告 (レベル 1) C4229

旧形式に使用されていますデータの修飾子は無視されます。

Microsoft の修飾子を使用して`__cdecl`データ宣言は旧式の手段です。

## <a name="example"></a>例

```
// C4229.cpp
// compile with: /W1 /LD
int __cdecl counter;   // C4229 cdecl ignored
```