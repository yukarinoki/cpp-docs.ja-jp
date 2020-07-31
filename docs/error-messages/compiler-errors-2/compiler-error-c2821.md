---
title: コンパイラ エラー C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: 115874724a24530e0d85256e11c3aa355aa4d6af
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225398"
---
# <a name="compiler-error-c2821"></a>コンパイラ エラー C2821

' operator new ' の最初の仮パラメーターは ' unsigned int ' でなければなりません

[Operator new](../../standard-library/new-operators.md#op_new)の最初の仮パラメーターは、符号なしである必要があり **`int`** ます。

## <a name="example"></a>例

次の例では、C2821 が生成されます。

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```
