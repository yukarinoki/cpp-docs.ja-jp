---
title: コンパイラ エラー C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: ded5a3d459e4b5d1412998aadbaa385864f505a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445553"
---
# <a name="compiler-error-c2243"></a>コンパイラ エラー C2243

'type1' から 'type2' の 'conversion type' 変換は存在しますが、アクセスできません。

アクセス保護 (`protected` または `private`) によって、派生クラスへのポインターから基底クラスへのポインターに変換できませんでした。

次の例では C2243 が生成されます。

```
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

`protected` または `private` アクセスの基底クラスは、派生クラスのクライアントからはアクセスできません。 これらのレベルのアクセス制御は、基底クラスが、クライアントに表示される必要がない実装の詳細であることを示すために使用されます。 派生クラスのクライアントが派生クラスのポインターから基底クラスへのポインターへの暗黙的な変換にアクセスする必要がある場合は、パブリック派生を使用します。