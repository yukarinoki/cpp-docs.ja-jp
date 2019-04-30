---
title: コンパイラ エラー C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: cd153bb5b331872bfe35b046d41612998bd0eff7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386006"
---
# <a name="compiler-error-c2178"></a>コンパイラ エラー C2178

'*識別子*'で宣言することはできません'*指定子*' 指定子

A`mutable`指定子は、宣言では、使用されましたが、このコンテキストでは、指定子は許可されません。

`mutable`指定子はクラスのデータ メンバーの名前にのみ適用できるし、宣言された名前には適用できません`const`または`static`メンバーを参照するには適用できません。

## <a name="example"></a>例

次の例では、どの C2178 が発生し、その修正方法を示します。

```
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
