---
title: コンパイラエラー C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: c4eb4a2551312791d05c8badb66af0070e74b630
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508330"
---
# <a name="compiler-error-c3170"></a>コンパイラエラー C3170

プロジェクト内で異なるモジュール識別子を持つことはできません

異なる名前の[モジュール](../../windows/attributes/module-cpp.md)属性が、コンパイルの2つのファイルに見つかりました。 コンパイルごとに指定できる一意の属性は1つだけ `module` です。

複数 `module` のソースコードファイルで、同一の属性を指定できます。

たとえば、次のモジュール属性が見つかったとします。

```cpp
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

この場合、次のようになります。

```cpp
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

コンパイラは C3170 を生成します (異なる名前に注意してください)。
