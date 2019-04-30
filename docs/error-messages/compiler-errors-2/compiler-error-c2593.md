---
title: コンパイラ エラー C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: c358553a36104b5c389076f5a5ce02f94f85e85a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386916"
---
# <a name="compiler-error-c2593"></a>コンパイラ エラー C2593

'operator identifier' があいまいです。

オーバー ロードされた演算子の 1 つ以上の可能な演算子が定義されます。

1 つまたは複数の実際のパラメーターで明示的なキャストを使用する場合、このエラーを修正しました可能性があります。

次の例では、C2593 が生成されます。

```
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

このエラーは、浮動小数点変数を使用して、シリアル化によって発生することができます、`CArchive`オブジェクト。 コンパイラの識別、`<<`演算子。 プリミティブのみの C++ の種類を`CArchive`をシリアル化できるが固定サイズ型`BYTE`、 `WORD`、 `DWORD`、および`LONG`します。 すべての整数型は、シリアル化のこれらの型のいずれかにキャストする必要があります。 浮動小数点型を使用してアーカイブする必要があります、`CArchive::Write()`メンバー関数。

次の例では、浮動小数点変数をアーカイブする方法を示しています (`f`) アーカイブに`ar`:

```
ar.Write(&f, sizeof( float ));
```