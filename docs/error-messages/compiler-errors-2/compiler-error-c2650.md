---
description: 詳細については、「コンパイラエラー C2650」を参照してください。
title: コンパイラエラー C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: 161b4a78f200a2fd6ca60d47c76b433624d2e1f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174547"
---
# <a name="compiler-error-c2650"></a>コンパイラエラー C2650

' operator ': 仮想関数にすることはできません。

**`new`** Or **`delete`** 演算子が宣言されて **`virtual`** います。 これらの演算子は **`static`** メンバー関数であり、にすることはできません **`virtual`** 。

## <a name="example"></a>例

次の例では、C2650 が生成されます。

```cpp
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```
