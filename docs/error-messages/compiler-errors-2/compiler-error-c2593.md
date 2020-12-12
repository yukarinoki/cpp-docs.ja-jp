---
description: 詳細については、「コンパイラエラー C2593」を参照してください。
title: コンパイラ エラー C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: 849cd79b1d469d957cf1bde499ce66bd54a64074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120166"
---
# <a name="compiler-error-c2593"></a>コンパイラ エラー C2593

' operator identifier ' があいまいです

オーバーロードされた演算子に対して、複数の使用可能な演算子が定義されています。

1つ以上の実際のパラメーターに対して明示的なキャストを使用すると、このエラーが解決される場合があります。

次の例では、C2593 が生成されます。

```cpp
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

このエラーは、オブジェクトを使用して浮動小数点変数をシリアル化することによって発生することがあり `CArchive` ます。 コンパイラは演算子を `<<` あいまいとして識別します。 シリアル化できるプリミティブ型の C++ 型は、 `CArchive` 固定サイズ型、 `BYTE` 、 `WORD` `DWORD` 、およびのみです `LONG` 。 シリアル化のために、すべての整数型をこれらの型のいずれかにキャストする必要があります。 浮動小数点型は、メンバー関数を使用してアーカイブする必要があり `CArchive::Write()` ます。

次の例は、浮動小数点変数 () をアーカイブするためにアーカイブする方法を示してい `f` `ar` ます。

```
ar.Write(&f, sizeof( float ));
```
