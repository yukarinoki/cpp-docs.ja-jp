---
title: コンパイラの警告 (レベル 1) C4441
ms.date: 11/04/2016
f1_keywords:
- C4441
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
ms.openlocfilehash: 45d7a6af09677c1e63dab5ffcc55c35d8203b40b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408239"
---
# <a name="compiler-warning-level-1-c4441"></a>コンパイラの警告 (レベル 1) C4441

'cc1' を無視する場合の呼び出し規約' cc2' の代わりに使用

管理対象のユーザー定義型とグローバル関数のジェネリック メンバー関数を使用する必要があります、 [_ _clrcall](../../cpp/clrcall.md)呼び出し規約。  使用されるコンパイラ`__clrcall`します。

## <a name="example"></a>例

次の例では、C4441 が生成されます。

```
// C4441.cpp
// compile with: /clr /W1 /c
generic <class ItemType>
void __cdecl Test(ItemType item) {}   // C4441
// try the following line instead
// void Test(ItemType item) {}

ref struct MyStruct {
   void __cdecl Test(){}   // C4441
   void Test2(){}   // OK
};
```