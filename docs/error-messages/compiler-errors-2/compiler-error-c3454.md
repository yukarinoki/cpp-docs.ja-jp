---
title: コンパイラ エラー C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 94c50ccd223567281e02c407e7ee22df75f859d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328602"
---
# <a name="compiler-error-c3454"></a>コンパイラ エラー C3454

[attribute] はクラス宣言では使用できません

クラスは、属性になるように定義する必要があります。

詳細については、「 [attribute](../../windows/attributes/attribute.md)」を参照してください。

## <a name="example"></a>例

次の例では C3454 が生成されます。

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```