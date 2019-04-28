---
title: コンパイラ エラー C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 7535f82a392f3d54b265ada2bd40a8d433838f4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227274"
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
