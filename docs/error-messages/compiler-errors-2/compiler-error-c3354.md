---
description: 詳細については、「コンパイラエラー C3354」を参照してください。
title: コンパイラ エラー C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: cb2c110471b95010e56677608725e5d6abeaa5e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245318"
---
# <a name="compiler-error-c3354"></a>コンパイラ エラー C3354

'function': デリゲートを作成するための関数に、戻り値の型 'type' を指定することはできません。

次の型は、の戻り値の型として無効です **`delegate`** 。

- 関数へのポインター

- メンバーへのポインター

- メンバー関数へのポインター

- 関数への参照

- メンバー関数への参照

次の例では C3354 が生成されます。

```cpp
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
