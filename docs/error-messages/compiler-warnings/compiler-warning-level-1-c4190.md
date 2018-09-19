---
title: コンパイラの警告 (レベル 1) C4190 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d398331c159c6fc639160dbe54d6ab5f969d3dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063737"
---
# <a name="compiler-warning-level-1-c4190"></a>コンパイラの警告 (レベル 1) C4190

'identifier1' が指定すると、C リンケージが UDT には C と互換性がない ' identifier2' を返します

関数または関数へのポインターは、戻り値の型として、UDT (ユーザー定義型、クラス、構造体、列挙型、または共用体である) を持つと`extern`"C"リンケージです。 これは、有効な場合。

- この関数に対するすべての呼び出しは、C++ から発生します。

- 関数の定義は、C++ では。

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