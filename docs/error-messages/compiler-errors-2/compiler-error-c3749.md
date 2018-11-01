---
title: コンパイラ エラー C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 7535f82a392f3d54b265ada2bd40a8d433838f4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596518"
---
# <a name="compiler-error-c3749"></a>コンパイラ エラー C3749

'attribute': 関数内で、カスタム属性を使用しない場合があります

カスタム属性は、関数内で使用できません。 カスタム属性の詳細については、トピックを参照してください。[属性](../../windows/attributes/attribute.md)します。

## <a name="example"></a>例

次の例では、C3749 が生成されます。

```
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
