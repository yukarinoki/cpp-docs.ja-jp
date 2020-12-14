---
description: 詳細については、「コンパイラエラー C3168」を参照してください。
title: コンパイラエラー C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: a6b9708ebb9c7fe3d9d6be7d73c24b92b1e8c6eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242250"
---
# <a name="compiler-error-c3168"></a>コンパイラエラー C3168

' type ': 列挙型の基になる型が正しくありません。

型に対して指定した基になる型 **`enum`** が有効ではありませんでした。 基になる型は、整数の C++ 型または対応する CLR 型である必要があります。

次の例では、C3168 が生成されます。

```cpp
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
