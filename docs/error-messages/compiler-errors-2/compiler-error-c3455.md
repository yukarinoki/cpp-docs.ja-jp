---
description: 詳細については、「コンパイラエラー C3455」を参照してください。
title: コンパイラ エラー C3455
ms.date: 11/04/2016
f1_keywords:
- C3455
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
ms.openlocfilehash: ae450f385111fd6fa6f7f5655d04f01f893b8fd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113637"
---
# <a name="compiler-error-c3455"></a>コンパイラ エラー C3455

'attribute': どの属性コンストラクターも引数に一致しませんでした

無効な値が属性の宣言に使用されました。  詳細については、「 [attribute](../../windows/attributes/attribute.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3455 が生成されます。

```cpp
// C3455.cpp
// compile with: /clr /c
using namespace System;

[attribute("MyAt")]   // C3455
// try the following line instead
// [attribute(All)]
ref struct MyAttr {
   MyAttr() {}
};
```
