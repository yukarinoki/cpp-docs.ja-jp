---
description: 詳細については、「コンパイラエラー C2488」を参照してください。
title: コンパイラ エラー C2488
ms.date: 11/04/2016
f1_keywords:
- C2488
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
ms.openlocfilehash: bb6a36749b630c4193174314f47a150f0981b0df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305495"
---
# <a name="compiler-error-c2488"></a>コンパイラ エラー C2488

' identifier ': ' 生 ' は、非メンバー関数の定義にのみ適用できます

関数宣言に [生](../../cpp/naked-cpp.md) の属性が適用されました。

次の例では、C2488 が生成されます。

```cpp
// C2488.cpp
// compile with: /c
// processor: x86
__declspec( naked ) void func();   // C2488  declaration, not definition
__declspec( naked ) void i;   // C2488  i is not a function

__declspec( naked ) void func() {}   // OK
```
