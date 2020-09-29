---
title: コンパイラ エラー C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: d6a0d1234d8f25c6a55fffa7170f37aae27f5817
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501320"
---
# <a name="compiler-error-c3451"></a>コンパイラ エラー C3451

' attribute ': アンマネージ属性を ' type ' に適用することはできません

C++ 属性を CLR 型に適用することはできません。 詳細については、「 [C++ 属性リファレンス](../../windows/attributes/attributes-alphabetical-reference.md) 」を参照してください。

詳細については、「 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

このエラーは、Visual Studio 2005 で実行されたコンパイラ準拠作業の結果として生成される可能性があります。ユーザー定義の属性では、CLR プログラミングを使用した [uuid](../../windows/attributes/uuid-cpp-attributes.md) 属性は許可されなくなりました。 代わりに <xref:System.Runtime.InteropServices.GuidAttribute> を使用してください

## <a name="example"></a>例

次の例では、C3451 が生成されます。

```cpp
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```
