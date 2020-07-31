---
title: コンパイラエラー C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: a40a79c48b0f437271063e555593464f55fe9837
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212593"
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
