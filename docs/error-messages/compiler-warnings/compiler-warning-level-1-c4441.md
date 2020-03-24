---
title: コンパイラの警告 (レベル 1) C4441
ms.date: 11/04/2016
f1_keywords:
- C4441
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
ms.openlocfilehash: 4de80a9b7ad5601d9f8760d7c55a64a8631307a8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162375"
---
# <a name="compiler-warning-level-1-c4441"></a>コンパイラの警告 (レベル 1) C4441

' cc1 ' の呼び出し規約は無視されます。代わりに ' cc2 ' が使用されています

マネージユーザー定義型およびグローバル関数ジェネリックのメンバー関数は、 [__clrcall](../../cpp/clrcall.md)の呼び出し規約を使用する必要があります。  コンパイラは `__clrcall`を使用しました。

## <a name="example"></a>例

次の例では、C4441 が生成されます。

```cpp
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
