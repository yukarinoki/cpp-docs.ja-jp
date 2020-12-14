---
description: 詳細については、「コンパイラエラー C3171」を参照してください。
title: コンパイラエラー C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 65e7e1db9a864b894a0bce825df09a372489a79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242198"
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
