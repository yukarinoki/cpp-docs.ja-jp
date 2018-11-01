---
title: コンパイラ エラー C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 68435610680e3b21415a1d9439a8133fd1e2557f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621664"
---
# <a name="compiler-error-c2079"></a>コンパイラ エラー C2079

'identifier' が定義されていないクラス、構造体、共用 'name' を使用します。

指定された識別子が、未定義のクラス、構造体または共用体です。

このエラーは、無名共用体を初期化することによって発生することができます。

次の例では、C2079 が生成されます。

```
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

考えられる解決方法:

```
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 は、前方宣言がスコープ内でのみが型のスタックにオブジェクトを宣言しようとした場合にも発生します。

```
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

考えられる解決方法:

```
// C2079d.cpp
// compile with: /c
class A;
class C {};

class B {
   A * a;
   C c;
};

class A {};
```