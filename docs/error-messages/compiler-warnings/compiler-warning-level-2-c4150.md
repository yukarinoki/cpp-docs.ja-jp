---
title: コンパイラの警告 (レベル 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: 4c5c10ee0ea3242e52e6db5391694c9ddf941a78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349777"
---
# <a name="compiler-warning-level-2-c4150"></a>コンパイラの警告 (レベル 2) C4150

不完全な型 'type' へのポインターの削除ないデストラクターが呼び出されます

**削除**演算子が、コンパイラはデストラクターを見つけることができませんので、宣言されましたが、定義されていない型を削除すると呼ばれます。

次の例では、C4150 が生成されます。

```
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```