---
title: コンパイラ エラー C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 98af3c84b48aa8e69ad883bf73299f2697618ce1
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501328"
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
