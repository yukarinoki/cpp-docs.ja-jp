---
title: コンパイラエラー C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 14f0cedc5448005a29d74f05ae3e68e74eb5cf1c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508304"
---
# <a name="compiler-error-c3171"></a>コンパイラエラー C3171

' module ': プロジェクトで異なるモジュール属性を指定することはできません

異なるパラメーターリストを持つ[モジュール](../../windows/attributes/module-cpp.md)属性が、コンパイルの2つのファイルに見つかりました。 コンパイルごとに指定できる一意の属性は1つだけ `module` です。

複数 `module` のソースコードファイルで、同一の属性を指定できます。

たとえば、次のような属性が見つかったとし `module` ます。

```cpp
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

この場合、次のようになります。

```cpp
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

コンパイラは C3171 を生成します (異なるバージョンの値に注意してください)。
