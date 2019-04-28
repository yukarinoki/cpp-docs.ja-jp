---
title: コンパイラ エラー C2630
ms.date: 11/04/2016
f1_keywords:
- C2630
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
ms.openlocfilehash: db4108961c940afe3333dc726a97a8ce6ae639a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222728"
---
# <a name="compiler-error-c2630"></a>コンパイラ エラー C2630

'symbol' で見つかりましたが、コンマ区切りの一覧にする必要があります。

コンマが必要なコンテキストで、シンボルが表示されます。

次の例では、C2630 が生成されます。

```
// C2630.cpp
// compile with: /c
struct D {
   D(int);
};

struct E {
   E(int);
};

class C : public D, public E {
   C();
};

C::C() : D(0) ; E(0) { }   // C2630
C::C() : D(0), E(0) {}   // OK
```