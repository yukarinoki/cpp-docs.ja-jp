---
title: コンパイラ エラー C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c7dac0abb7d65d3f26522ea1a04577643b7b9eca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212827"
---
# <a name="compiler-error-c2246"></a>コンパイラ エラー C2246

'identifier': ローカルに定義されたクラスの静的データ メンバーが正しくありません

ローカルスコープのクラス、構造体、または共用体のメンバーがとして宣言されて **`static`** います。

次の例では C2246 が生成されます。

```cpp
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```
