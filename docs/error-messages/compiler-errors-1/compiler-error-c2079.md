---
description: 詳細については、「コンパイラエラー C2079」を参照してください。
title: コンパイラエラー C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 73ca5d334ac3bf3157b61a1b2a9489282ae1fe00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151217"
---
# <a name="compiler-error-c2079"></a>コンパイラエラー C2079

' identifier ' は未定義のクラス/構造体/共用体 ' name ' を使用します

指定された識別子は、未定義のクラス、構造体、または共用体です。

このエラーは、匿名共用体を初期化することによって発生することがあります。

次の例では、C2079 が生成されます。

```cpp
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

考えられる解決策:

```cpp
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 は、前方宣言がスコープ内にのみ存在する型のスタック上でオブジェクトを宣言しようとした場合にも発生する可能性があります。

```cpp
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

考えられる解決策:

```cpp
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
