---
description: '詳細情報: コンパイラの警告 (レベル 1) C4550'
title: コンパイラの警告 (レベル 1) C4550
ms.date: 11/04/2016
f1_keywords:
- C4550
helpviewer_keywords:
- C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
ms.openlocfilehash: 8edb7744f522312933bcf9d273982e591918dac2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265975"
---
# <a name="compiler-warning-level-1-c4550"></a>コンパイラの警告 (レベル 1) C4550

式は引数リストのない関数に評価されます

関数への逆参照ポインターに引数リストがありません。

## <a name="example"></a>例

```cpp
// C4550.cpp
// compile with: /W1
bool f()
{
   return true;
}

typedef bool (*pf_t)();

int main()
{
   pf_t pf = f;
   if (*pf) {}  // C4550
   return 0;
}
```
