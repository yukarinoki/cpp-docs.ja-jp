---
title: コンパイラの警告 (レベル 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 6d110aa70a470382e274546e95599804fa3bc7d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199876"
---
# <a name="compiler-warning-level-1-c4190"></a>コンパイラの警告 (レベル 1) C4190

' identifier1 ' には C リンケージが指定されていますが、C と互換性のない UDT ' identifier2 ' が返されます

関数への関数またはポインターには、戻り値の型と `extern` "C" リンケージとして UDT (ユーザー定義型、クラス、構造体、列挙型、または共用体) があります。 次の場合に有効です。

- この関数のすべての呼び出しはC++、から発生します。

- 関数の定義はにC++あります。

## <a name="example"></a>例

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
