---
description: 詳細については、「コンパイラエラー C3865」を参照してください。
title: コンパイラ エラー C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 956cbfeb5bac97cae7e9a9a411c29326062e15b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222880"
---
# <a name="compiler-error-c3865"></a>コンパイラ エラー C3865

' calling_convention ': ネイティブメンバー関数でのみ使用できます

呼び出し規約が、グローバル関数またはマネージメンバー関数のいずれかであった関数で使用されました。 呼び出し規約は、ネイティブ (管理されていない) メンバー関数でのみ使用できます。

詳細については、「 [呼び出し規則](../../cpp/calling-conventions.md)」を参照してください。

次の例では、C3865 が生成されます。

```cpp
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```
