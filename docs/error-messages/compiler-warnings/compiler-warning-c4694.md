---
description: 詳細については、「コンパイラの警告 C4694」を参照してください。
title: コンパイラの警告 C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: f6a6890fab320c2471381076707eeca30ce3e99b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315076"
---
# <a name="compiler-warning-c4694"></a>コンパイラの警告 C4694

> '*class*': シールドされた抽象クラスは、基底クラス '*base_class*' を持つことはできません

シールされた抽象クラスは参照型を継承できません。シールされた抽象クラスは、基底クラスの関数を実装することも、それ自体を基底クラスとして使用しすることもできません。

詳細については、「 [abstract](../../extensions/abstract-cpp-component-extensions.md)、 [Sealed](../../extensions/sealed-cpp-component-extensions.md)、および [Classes and struct](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

この警告は、自動的にエラーになります。 この動作を変更する場合は、 [#pragma 警告](../../preprocessor/warning.md)を使用します。

## <a name="example"></a>例

次の例では C4694 が生成されます。

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```
