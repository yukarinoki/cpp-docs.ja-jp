---
description: 詳細については、「コンパイラエラー C2663」を参照してください。
title: コンパイラエラー C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: 3e70e2d10b0a133769d92ce637bd9e5f4d44315a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169984"
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
