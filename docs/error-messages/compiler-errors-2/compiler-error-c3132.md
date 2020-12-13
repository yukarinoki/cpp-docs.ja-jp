---
description: 詳細については、「コンパイラエラー C3132」を参照してください。
title: コンパイラエラー C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: e81ddcb977342a687dce329239a590f90eca67ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177394"
---
# <a name="compiler-error-c3132"></a>コンパイラエラー C3132

' 関数パラメーター ': パラメーター配列は、型 ' single 次元マネージ配列 ' の仮引数にのみ適用できます

属性が、 <xref:System.ParamArrayAttribute> 1 次元配列ではないパラメーターに適用されました。

次の例では、C3132 が生成されます。

```cpp
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```
