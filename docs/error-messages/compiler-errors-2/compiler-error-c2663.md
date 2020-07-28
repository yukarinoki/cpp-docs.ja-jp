---
title: コンパイラエラー C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: f9746ecb41e873fb1d929a939c78f1817dc0e2f9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220276"
---
# <a name="compiler-error-c2663"></a>コンパイラエラー C2663

' function ': 数値オーバーロードに ' this ' ポインターの有効な変換がありません

コンパイラは、 **`this`** メンバー関数のオーバーロードされたバージョンに変換できませんでした。

このエラーは、オブジェクトに対して非メンバー関数を呼び出すことによって発生することがあり **`const`** **`const`** ます。  考えられる解決策は次のとおりです。

1. **`const`** オブジェクト宣言からを削除します。

1. **`const`** メンバー関数のオーバーロードのいずれかにを追加します。

次の例では、C2663 が生成されます。

```cpp
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
