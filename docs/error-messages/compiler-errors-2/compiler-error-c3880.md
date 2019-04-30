---
title: コンパイラ エラー C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 0b169309db88291f8a83b6d1192787b6396e84a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338468"
---
# <a name="compiler-error-c3880"></a>コンパイラ エラー C3880

'var': リテラル データ メンバーにすることはできません

種類、[リテラル](../../extensions/literal-cpp-component-extensions.md)属性がある必要があります、または、次の種類のいずれかに、コンパイル時に変換できます。

- 整数型

- string

- 整数または基になる型を持つ列挙型

次の例では、C3880 が生成されます。

```
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```