---
description: 詳細については、「コンパイラエラー C2246」を参照してください。
title: コンパイラ エラー C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: 1868389c98dd864e7d92bf33d57dbe96b831f3e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302205"
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
