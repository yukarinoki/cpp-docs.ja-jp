---
title: コンパイラ エラー C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 846657d3598e268d78ff3c39f2bfc901756ad370
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642776"
---
# <a name="compiler-error-c3865"></a>コンパイラ エラー C3865

'calling_convention': ネイティブ メンバー関数でのみ使用できます

グローバル関数が関数またはマネージ メンバー関数、呼び出し規約が使用されました。 呼び出し規約は、ネイティブの (管理されていない) メンバー関数でのみ使用できます。

詳細については、[呼び出し規則](../../cpp/calling-conventions.md)を参照してください。

次の例では、C3865 が生成されます。

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```