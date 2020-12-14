---
description: 詳細については、「コンパイラエラー C3880」を参照してください。
title: コンパイラ エラー C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: c2d279cd50716f647fbbdf51f9f9c39863d4e2d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274594"
---
# <a name="compiler-error-c3880"></a>コンパイラ エラー C3880

' var ': リテラルデータメンバーにすることはできません。

[リテラル](../../extensions/literal-cpp-component-extensions.md)属性の型は、次のいずれかの型であるか、コンパイル時に変換可能である必要があります。

- 整数型

- string

- 整数型または基になる型を持つ列挙型

次の例では、C3880 が生成されます。

```cpp
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```
