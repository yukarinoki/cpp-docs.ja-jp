---
title: コンパイラ エラー C3451 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8685b75684827b4f202317e1df72a8248f1b41dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085200"
---
# <a name="compiler-error-c3451"></a>コンパイラ エラー C3451

'attribute': 'type' に非管理対象の属性を適用することはできません

C++ 属性は、CLR 型に適用できません。 参照してください[C++ 属性リファレンス](../../windows/cpp-attributes-reference.md)詳細についてはします。

詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます。 [uuid](../../windows/uuid-cpp-attributes.md)属性は CLR プログラミングを使用してユーザー定義の属性では使用できなくします。 代わりに、<xref:System.Runtime.InteropServices.GuidAttribute> を使用してください。

## <a name="example"></a>例

次の例では、C3451 が生成されます。

```
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