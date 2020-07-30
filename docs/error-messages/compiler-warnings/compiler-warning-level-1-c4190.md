---
title: コンパイラの警告 (レベル 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 8187926f2477a4d3f1ca3019cc8c3c71710c1dff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233302"
---
# <a name="compiler-warning-level-1-c4190"></a>コンパイラの警告 (レベル 1) C4190

' identifier1 ' には C リンケージが指定されていますが、C と互換性のない UDT ' identifier2 ' が返されます

関数への関数またはポインターには、戻り値の型とリンケージとして UDT (ユーザー定義型、つまりクラス、構造体、列挙型、または共用体) があり `extern "C"` ます。 次の場合に有効です。

- この関数のすべての呼び出しは、C++ から発生します。

- 関数の定義は C++ で定義されています。

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
