---
description: '詳細情報: コンパイラの警告 (レベル 1) C4190'
title: コンパイラの警告 (レベル 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: ff27d5913e23fa1488816b3e2bb7284440c7577b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266586"
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
