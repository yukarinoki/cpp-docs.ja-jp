---
title: コンパイラ エラー C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: 2737f9078e1c17358e3c975a5c3f8b6d211fd308
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165776"
---
# <a name="compiler-error-c2575"></a>コンパイラ エラー C2575

'identifier': メンバー関数とベースを仮想にすることができますのみ

グローバル関数またはクラスが宣言される`virtual`します。 これは認められていません。

次の例では、C2575 が生成されます。

```
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```