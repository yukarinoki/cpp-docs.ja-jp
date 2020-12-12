---
description: 詳細については、「コンパイラエラー C2477」を参照してください。
title: コンパイラ エラー C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 50cbb3523e6dc30dc465876435db40a80e2768fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164394"
---
# <a name="compiler-error-c2477"></a>コンパイラ エラー C2477

' member ': 静的データメンバーを派生クラスで初期化することはできません

テンプレートクラスの静的データメンバーが正しく初期化されませんでした。 これは、ISO C++ 標準に準拠するために、Visual Studio .NET 2003 より前のバージョンの Microsoft C++ コンパイラの互換性に影響する変更点です。

次の例では、C2477 が生成されます。

```cpp
// C2477.cpp
// compile with: /Za /c
template <class T>
struct S {
   static int n;
};

struct X {};
struct A: S<X> {};

int A::n = 0;   // C2477

template<>
int S<X>::n = 0;
```
