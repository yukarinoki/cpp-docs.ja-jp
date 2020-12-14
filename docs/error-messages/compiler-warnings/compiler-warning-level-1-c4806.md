---
description: '詳細情報: コンパイラの警告 (レベル 1) C4806'
title: コンパイラの警告 (レベル 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: 3e4aaa67c2a979afde2d1a7643d0c5ab1b879418
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238246"
---
# <a name="compiler-warning-level-1-c4806"></a>コンパイラの警告 (レベル 1) C4806

'operation': 安全でない演算: 'type' 型から 'type' 型への上位変換を行うと与えられた定数に等しくなりません

このメッセージ `b == 3` は、が型であるなどのコードに対して警告し `b` **`bool`** ます。 昇格規則によって、が **`bool`** に昇格され **`int`** ます。 これは有効ですが、にすることはできません **`true`** 。 次の例では C4806 が生成されます。

```cpp
// C4806.cpp
// compile with: /W1
int main()
{
   bool b = true;
   // try..
   // int b = true;

   if (b == 3)   // C4806
   {
      b = false;
   }
}
```
