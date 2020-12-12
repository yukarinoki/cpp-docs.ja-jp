---
description: 詳細については、「コンパイラエラー C2429」を参照してください。
title: コンパイラエラー C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 3c16a2a430e8050103c3903cf1355de089252ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190134"
---
# <a name="compiler-error-c2429"></a>コンパイラエラー C2429

> '*language feature*' にはコンパイラフラグ '*compiler option*' が必要です

言語機能には、サポートのための特定のコンパイラオプションが必要です。

エラー **C2429: 言語機能 ' nested-namespace-definition ' が必要です** 。これは、Visual Studio 2015 Update 5 以降で入れ子になった名前空間 *名を 1* つ以上含む名前空間を定義しようとすると、コンパイラフラグ '/std: c++ 17 ' が生成されます。 (Visual Studio 2017 バージョン15.3 では、 **/std: c + + latest** スイッチが必要です)。C++ 17 より前の C++ では、複合名前空間の定義は許可されていません。 コンパイラは、 [/std: c++ 17](../../build/reference/std-specify-language-standard-version.md) コンパイラオプションが指定されている場合に、複合名前空間の定義をサポートします。

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual Studio 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
