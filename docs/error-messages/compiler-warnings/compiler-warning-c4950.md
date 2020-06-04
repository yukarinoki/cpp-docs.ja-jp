---
title: コンパイラの警告 C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: 52c4de94dfe087b4dcf407295e556c9350b2cb8b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164990"
---
# <a name="compiler-warning-c4950"></a>コンパイラの警告 C4950

'type_or_member': obsolete としてマークされています

メンバーまたは型が、<xref:System.ObsoleteAttribute> 属性で obsolete とマークされました。

C4950 は、常にエラーとして表示されます。 この警告は、 [warning](../../preprocessor/warning.md)プラグマディレクティブまたは[/wd](../../build/reference/compiler-option-warning-level.md)コンパイラオプションを使用して無効にすることができます。

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
