---
title: コンパイラ エラー C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: d313168e8033395da1749e000e52421939f77af4
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686653"
---
# <a name="compiler-error-c3699"></a>コンパイラ エラー C3699

' operator ': この間接参照を型 ' type ' で使用することはできません

で許可されていない間接参照を使用しようとしました `type` 。

## <a name="examples"></a>例

次の例では、C3699 が生成されます。

```cpp
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

Trivial プロパティに参照型を含めることはできません。 詳細については、「 [property](../../extensions/property-cpp-component-extensions.md) 」を参照してください。 次の例では、C3699 が生成されます。

```cpp
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

"ポインターへのポインター" 構文に相当するものは、追跡参照へのハンドルです。 次の例では、C3699 が生成されます。

```cpp
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```
