---
title: コンパイラ エラー C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: e413e4a08ce22ef109179ff0f98baf32ebba41c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525845"
---
# <a name="compiler-error-c3699"></a>コンパイラ エラー C3699

'operator': 型 'type' でこの間接参照を使用することはできません

許可されていない間接指定を使用しようとした`type`します。

## <a name="example"></a>例

次の例では、C3699 が生成されます。

```
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>例

Trivial プロパティには、参照型を含めることはできません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。 次の例では、C3699 が生成されます。

```
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>例

同等の「ポインターへのポインター」構文は、追跡参照を識別するハンドルです。 次の例では、C3699 が生成されます。

```
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```