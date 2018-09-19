---
title: コンパイラ エラー C3699 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3699
dev_langs:
- C++
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64e5a5bb98f9e8a6950bbb279c026f167a2ee92e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107715"
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