---
title: コンパイラ エラー C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: d74326e49edd980896276e2c6e67526d8d769cb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644341"
---
# <a name="compiler-error-c2663"></a>コンパイラ エラー C2663

'function': 'this' ポインターの有効な変換がある数のオーバー ロードがありません

コンパイラは変換できませんでした`this`任意のメンバー関数のオーバー ロードされたバージョンにします。

このエラーは、以外を呼び出すことによって発生することができます`const`でメンバー関数、`const`オブジェクト。  考えられる解決策:

1. 削除、`const`オブジェクトの宣言から。

1. 追加`const`メンバー関数のオーバー ロードのいずれかにします。

次の例では、C2663 が生成されます。

```
// C2663.cpp
struct C {
   void f() volatile {}
   void f() {}
};

struct D {
   void f() volatile;
   void f() const {}
};

const C *pcc;
const D *pcd;

int main() {
   pcc->f();    // C2663
   pcd->f();    // OK
}
```