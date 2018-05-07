---
title: コンパイラ エラー C2593 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2593
dev_langs:
- C++
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e419416266e0e3c4ebff8190b3b26b1c43c9ba0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2593"></a>コンパイラ エラー C2593
'operator identifier' があいまいです。  
  
 可能な演算子が 1 つ以上のオーバー ロードされた演算子が定義されます。  
  
 1 つまたは複数の実引数の明示的なキャストを使用する場合、このエラーを解決する可能性があります。  
  
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
  
 このエラーは、浮動小数点変数を使用して、シリアル化によって発生することができます、`CArchive`オブジェクト。 コンパイラの識別、`<<`演算子があいまいであるとします。 プリミティブのみの C++ の種類を`CArchive`をシリアル化できる固定サイズの種類は、 `BYTE`、 `WORD`、 `DWORD`、および`LONG`です。 すべての整数型は、シリアル化のこれらの型のいずれかにキャストする必要があります。 使用して浮動小数点型をアーカイブする必要があります、`CArchive::Write()`メンバー関数。  
  
 次の例に、浮動小数点変数をアーカイブする方法を示しています (`f`) アーカイブに`ar`:  
  
```  
ar.Write(&f, sizeof( float ));  
```