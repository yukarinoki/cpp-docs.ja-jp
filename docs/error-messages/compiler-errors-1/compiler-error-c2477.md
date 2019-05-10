---
title: コンパイラ エラー C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 73d8daa9576e4edc29958918c107e9edf18cc579
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447975"
---
# <a name="compiler-error-c2477"></a>コンパイラ エラー C2477

'member': 静的データ メンバーは派生クラスを使って初期化できません

テンプレート クラスの静的データ メンバーが正しく初期化されていません。 これは、Microsoft のバージョンと互換性に影響する変更C++、ISO に準拠するために、Visual Studio .NET 2003 より前のコンパイラC++標準。

次の例では、C2477 が生成されます。

```
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