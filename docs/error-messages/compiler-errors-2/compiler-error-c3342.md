---
description: 詳細については、「コンパイラエラー C3342」を参照してください。
title: コンパイラ エラー C3342
ms.date: 11/04/2016
f1_keywords:
- C3342
helpviewer_keywords:
- C3342
ms.assetid: 5c6d784f-bebe-4f7e-8615-44ca6f78bfba
ms.openlocfilehash: dfbeada49972832c238acb6c0fa656e3e75d7089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337305"
---
# <a name="compiler-error-c3342"></a>コンパイラ エラー C3342

'attribute': あいまいな属性です

コンパイラが 1 つの属性の定義を複数検出しました。

属性が複数回定義されています。

詳細については、「 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3342 が生成されます。

```cpp
// C3342.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Reflection;

[AttributeUsage(AttributeTargets::All)]
public ref class XAttribute : public  Attribute {};

[AttributeUsage(AttributeTargets::All)]
public ref class X : public Attribute {};

[X]   // C3342 could refer to X or XAttribute
// try the following line instead
// [XAttribute]
public ref class Class4 {};
```
