---
description: 詳細については、「コンパイラエラー C3749」を参照してください。
title: コンパイラ エラー C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 247f98214a3f2ec8a496f1da11633f53916328f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340178"
---
# <a name="compiler-error-c3749"></a>コンパイラ エラー C3749

' attribute ': カスタム属性を関数内で使用することはできません

カスタム属性は関数内では使用できません。 カスタム属性の詳細については [、「」](../../windows/attributes/attribute.md)を参照してください。

## <a name="example"></a>例

次の例では、C3749 が生成されます。

```cpp
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
