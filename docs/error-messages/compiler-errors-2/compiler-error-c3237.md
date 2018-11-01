---
title: コンパイラ エラー C3237
ms.date: 11/04/2016
f1_keywords:
- C3237
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
ms.openlocfilehash: 9853fd67c2b053e337cfacb5478e206c79321263
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631778"
---
# <a name="compiler-error-c3237"></a>コンパイラ エラー C3237

'generic_class' : ジェネリック クラスをカスタム属性にすることはできません

ジェネリック クラスは、ユーザー定義の属性にすることはできません。

## <a name="example"></a>例

次の例では C3237 が生成されます。

```
// C3237.cpp
// compile with: /clr /c
// C3237 expected
using namespace System;

generic <class T>
// Delete the following line to resolve.
[attribute(AttributeTargets::All, AllowMultiple=true)]
public ref class GR {};
```