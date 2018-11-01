---
title: コンパイラの警告 (レベル 4) C4515
ms.date: 11/04/2016
f1_keywords:
- C4515
helpviewer_keywords:
- C4515
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
ms.openlocfilehash: 147855f607d8ca72aa32548bf817484b6c0c3cfe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459658"
---
# <a name="compiler-warning-level-4-c4515"></a>コンパイラの警告 (レベル 4) C4515

'namespace': 名前空間を使用して自体

名前空間は、再帰的に使用します。

次の例では、C4515 が生成されます。

```
// C4515.cpp
// compile with: /W4
namespace A
{
   using namespace A; // C4515
}

int main()
{
}
```