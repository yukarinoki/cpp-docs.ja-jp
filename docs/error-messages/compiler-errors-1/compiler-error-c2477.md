---
title: コンパイラ エラー C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 27db194cb308d711a259127b628c60b4d10b94ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383231"
---
# <a name="compiler-error-c2477"></a>コンパイラ エラー C2477

'member': 静的データ メンバーは派生クラスを使って初期化できません

テンプレート クラスの静的データ メンバーが正しく初期化されていません。 これは、ISO C 標準に準拠するために Visual Studio .NET 2003 では、前に、Visual C コンパイラのバージョンと互換性に影響する変更です。

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