---
description: 詳細については、「コンパイラエラー C3454」を参照してください。
title: コンパイラ エラー C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 3d7905600a5d9502315689f9d25bd6d39dd80763
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315934"
---
# <a name="compiler-error-c3454"></a>コンパイラ エラー C3454

[attribute] はクラス宣言では使用できません

クラスは、属性になるように定義する必要があります。

詳細については、「 [attribute](../../windows/attributes/attribute.md)」を参照してください。

## <a name="example"></a>例

次の例では C3454 が生成されます。

```cpp
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```
