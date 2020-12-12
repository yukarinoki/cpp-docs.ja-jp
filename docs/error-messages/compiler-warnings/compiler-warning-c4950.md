---
description: 詳細については、「コンパイラの警告 C4950」を参照してください。
title: コンパイラの警告 C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: e1bb05501fcac6c836bfd4aa89f72807b625c292
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314881"
---
# <a name="compiler-warning-c4950"></a>コンパイラの警告 C4950

'type_or_member': 廃止としてマークされています

メンバーまたは型が属性で obsolete とマークされました <xref:System.ObsoleteAttribute> 。

C4950 は、常にエラーとして表示されます。 この警告は、 [warning](../../preprocessor/warning.md) プラグマディレクティブまたは [/wd](../../build/reference/compiler-option-warning-level.md) コンパイラオプションを使用して無効にすることができます。

## <a name="example"></a>例

次の例では C4950 が生成されます。

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```
