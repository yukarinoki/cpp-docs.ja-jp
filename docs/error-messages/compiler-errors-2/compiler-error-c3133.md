---
description: 詳細については、「コンパイラエラー C3133」を参照してください。
title: コンパイラエラー C3133
ms.date: 11/04/2016
f1_keywords:
- C3133
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
ms.openlocfilehash: 3559e5864ea5f8d5e690a77899d6314ee2b65519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177381"
---
# <a name="compiler-error-c3133"></a>コンパイラエラー C3133

C++ varargs に属性を適用することはできません

属性が正しく適用されませんでした。 変数引数を表す省略記号に属性を適用することはできません。

詳細については、「 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3133 が生成されます。

```cpp
// C3133.cpp
// compile with: /clr /c
ref struct MyAttr: System::Attribute {};
void Func([MyAttr]...);   // C3133
void Func2([MyAttr] int i);   // OK
```
