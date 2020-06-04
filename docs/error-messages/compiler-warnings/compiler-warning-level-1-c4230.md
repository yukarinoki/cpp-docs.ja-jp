---
title: コンパイラの警告 (レベル 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: be402eed4474dd736ab237cfb5c7986741338eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163272"
---
# <a name="compiler-warning-level-1-c4230"></a>コンパイラの警告 (レベル 1) C4230

旧形式: 修飾子/修飾子が混在しています。修飾子が無視されました

`__cdecl` などの Microsoft 修飾子の前に修飾子を使用することは、古い方法です。

## <a name="example"></a>例

```cpp
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```
