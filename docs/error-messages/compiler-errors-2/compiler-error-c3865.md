---
title: コンパイラ エラー C3865 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fd5c83d922601ca4cdffe0f3772723b31e630b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090842"
---
# <a name="compiler-error-c3865"></a>コンパイラ エラー C3865

'calling_convention': ネイティブ メンバー関数でのみ使用できます

グローバル関数が関数またはマネージ メンバー関数、呼び出し規約が使用されました。 呼び出し規約は、ネイティブの (管理されていない) メンバー関数でのみ使用できます。

詳細については、次を参照してください。[呼び出し規則](../../cpp/calling-conventions.md)します。

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