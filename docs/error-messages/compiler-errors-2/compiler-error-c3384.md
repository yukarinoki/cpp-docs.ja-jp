---
description: 詳細については、「コンパイラエラー C3384」を参照してください。
title: コンパイラ エラー C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: 79d5aabf185702c3d85485744b14e714a32aa76b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285579"
---
# <a name="compiler-error-c3384"></a>コンパイラ エラー C3384

'type_parameter': 値の制約および ref 制約を同時に使用することはできません

ジェネリック型をとの両方に制限することはできません **`value class`** **`ref class`** 。

詳細については、「 [ジェネリック型パラメーターの制約 (C++/cli)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3384 が生成されます。

```cpp
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```
