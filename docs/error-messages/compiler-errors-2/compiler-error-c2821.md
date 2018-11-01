---
title: コンパイラ エラー C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: 5c725d9648a7800c68a2fbff20e594a400c296c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632548"
---
# <a name="compiler-error-c2821"></a>コンパイラ エラー C2821

最初の仮パラメーター 'operator new' は 'unsigned int' である必要があります。

最初の仮パラメーター、[演算子 new](../../standard-library/new-operators.md#op_new) unsigned にする必要があります`int`します。

## <a name="example"></a>例

次の例では、C2821 が生成されます。

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```