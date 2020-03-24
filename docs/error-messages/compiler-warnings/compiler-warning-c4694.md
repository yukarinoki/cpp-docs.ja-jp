---
title: コンパイラの警告 C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: daf5423588d08260239c3cff5a68532a358d07b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165120"
---
# <a name="compiler-warning-c4694"></a>コンパイラの警告 C4694

> '*class*': シールドされた抽象クラスは、基底クラス '*base_class*' を持つことはできません

シールされた抽象クラスは参照型を継承できません。シールされた抽象クラスは、基底クラスの関数を実装することも、それ自体を基底クラスとして使用しすることもできません。

詳細については、「 [abstract](../../extensions/abstract-cpp-component-extensions.md)、 [Sealed](../../extensions/sealed-cpp-component-extensions.md)、および[Classes and struct](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

この警告は、自動的にエラーになります。 この動作を変更する場合は、 [#pragma 警告](../../preprocessor/warning.md)を使用します。

## <a name="example"></a>例

次の例では C4694 が生成されます。

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```
