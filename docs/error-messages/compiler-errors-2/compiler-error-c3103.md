---
title: コンパイラ エラー C3103
ms.date: 11/04/2016
f1_keywords:
- C3103
helpviewer_keywords:
- C3103
ms.assetid: 7984bd3e-d51d-43e4-b6f4-08c1e9fb9704
ms.openlocfilehash: 8dae731e36177dc199554615f74e92ebc5f6f5dc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531947"
---
# <a name="compiler-error-c3103"></a>コンパイラ エラー C3103

'argument': 名前付き引数を繰り返す

属性は、名前付き引数を繰り返さないことができます。

詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3103 が生成されます。

```
// C3103.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref class Attr : public Attribute {
public:
   int m_t;
};

[Attr(m_t = 10, m_t = 1)]   // C3103
// try the following line instead
// [Attr(m_t = 10)]
ref class A {};
```