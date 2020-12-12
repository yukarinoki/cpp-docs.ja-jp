---
description: 詳細については、「コンパイラエラー C3062」を参照してください。
title: コンパイラ エラー C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: b57d03f3ef09e1d01741866d99dfff87aa5aa28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281744"
---
# <a name="compiler-error-c3062"></a>コンパイラ エラー C3062

' enum ': 基になる型が ' type ' であるため、列挙子には値が必要です

列挙型の基になる型を指定できます。 ただし、一部の型では、各列挙子に値を代入する必要があります。

列挙型の詳細については、「 [enum class](../../extensions/enum-class-cpp-component-extensions.md)」を参照してください。

次の例では、C3062 が生成されます。

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
