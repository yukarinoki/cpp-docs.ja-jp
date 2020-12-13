---
description: '詳細情報: コンパイラの警告 (レベル 2) C4150'
title: コンパイラの警告 (レベル 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: 9b0296b94bbb2aab18b579898f053e002397c04e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177251"
---
# <a name="compiler-warning-level-2-c4150"></a>コンパイラの警告 (レベル 2) C4150

不完全な型 ' type ' へのポインターを削除しています。デストラクターが呼び出されません

**`delete`** 演算子は、宣言されているが定義されていない型を削除するために呼び出されます。そのため、コンパイラはデストラクターを見つけることができません。

次の例では、C4150 が生成されます。

```cpp
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
