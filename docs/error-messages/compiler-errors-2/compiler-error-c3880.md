---
title: コンパイラ エラー C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 60b96a9e704215ec1cbbab63eb77ca5d43ccb627
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626942"
---
# <a name="compiler-error-c3880"></a>コンパイラ エラー C3880

'var': リテラル データ メンバーにすることはできません

種類、[リテラル](../../windows/literal-cpp-component-extensions.md)属性がある必要があります、または、次の種類のいずれかに、コンパイル時に変換できます。

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