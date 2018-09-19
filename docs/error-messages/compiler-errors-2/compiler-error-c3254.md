---
title: コンパイラ エラー C3254 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e42071c55ef3c7a4fc950b1b25656cf68d4024
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081183"
---
# <a name="compiler-error-c3254"></a>コンパイラ エラー C3254

'明示的なオーバーライド': クラスは、明示的なオーバーライド 'override' が含まれていますが、関数宣言を含むインターフェイスから派生していません

ときにする[を明示的にオーバーライド](../../cpp/explicit-overrides-cpp.md)メソッド、クラス、オーバーライドを含む必要があります、直接または間接的に派生、オーバーライドする関数を含む型から。

次の例では、C3254 が生成されます。

```
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```