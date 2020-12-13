---
description: 詳細については、「コンパイラエラー C3320」を参照してください。
title: コンパイラ エラー C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 2dde804792dec4f7a1564c680a45c78adf60eedf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337372"
---
# <a name="compiler-error-c3320"></a>コンパイラ エラー C3320

'type': 型には、モジュール 'name' プロパティと同じ名前を指定することはできません

エクスポートされたユーザー定義型 (UDT) は、構造体、クラス、列挙型、または共用体である可能性がありますが、 [モジュール](../../windows/attributes/module-cpp.md) 属性の name プロパティに渡されたパラメーターと同じ名前を持つことはできません。

## <a name="example"></a>例

次の例では C3320 が生成されます。

```cpp
// C3320.cpp
#include "unknwn.h"
[module(name="xx")];

[export] struct xx {   // C3320
// Try the following line instead
// [export] struct yy {
   int i;
};
```
