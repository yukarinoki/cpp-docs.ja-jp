---
title: コンパイラ エラー C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 6f4157db4a2a1b1864446a082deddc73df2e2fe9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778710"
---
# <a name="compiler-error-c3062"></a>コンパイラ エラー C3062

'enum': 基になる型は 'type' であるために、列挙子から値が必要です

列挙体は、基になる型を指定することができます。 ただし、一部の種類には、列挙子ごとに値を代入する必要があります。

列挙型の詳細については、次を参照してください。[列挙型クラス](../../extensions/enum-class-cpp-component-extensions.md)します。

次の例では、C3062 が生成されます。

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```