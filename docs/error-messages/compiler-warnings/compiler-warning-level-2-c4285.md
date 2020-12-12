---
description: '詳細情報: コンパイラの警告 (レベル 2) C4285'
title: コンパイラの警告 (レベル 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 2eafb9bb17c5e6ea782ff00900c410727b3b39f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173585"
---
# <a name="compiler-warning-level-2-c4285"></a>コンパイラの警告 (レベル 2) C4285

挿入辞表記を使用して適用された場合、' identifier:: operator-> ' の戻り値の型は再帰的です

指定された **operator-> ()** 関数は、定義されている型、またはそれが定義されている型への参照を返すことができません。

次の例では、C4285 が生成されます。

```cpp
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```
