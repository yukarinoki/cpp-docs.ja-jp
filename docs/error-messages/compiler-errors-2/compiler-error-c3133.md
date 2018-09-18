---
title: コンパイラ エラー C3133 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3133
dev_langs:
- C++
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 269cc2c22d260b058f16263e4ee73e4a480920eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023398"
---
# <a name="compiler-error-c3133"></a>コンパイラ エラー C3133

C++ varargs に属性を適用することはできません。

属性が正しく適用されませんでした。 属性を適用して、変数の引数を表す省略記号にことはできません。

詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3133 が生成されます。

```
// C3133.cpp
// compile with: /clr /c
ref struct MyAttr: System::Attribute {};
void Func([MyAttr]...);   // C3133
void Func2([MyAttr] int i);   // OK
```