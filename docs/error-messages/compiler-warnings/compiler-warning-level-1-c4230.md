---
title: コンパイラの警告 (レベル 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: c8d223a286b8d42ca404fbfe7cbc51b67b3dd497
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529660"
---
# <a name="compiler-warning-level-1-c4230"></a>コンパイラの警告 (レベル 1) C4230

旧形式に使用されています: 修飾子/混在;修飾子は無視されます。

Microsoft の修飾子の前に、修飾子を使用して`__cdecl`旧式の手段です。

## <a name="example"></a>例

```
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```