---
title: コンパイラ エラー C2429 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/16/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 032df433b28e83f720fe76952a541b59bda889f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2429"></a>コンパイラ エラー C2429

> '*言語機能*'コンパイラ フラグが必要'*コンパイラ オプション*'

言語機能には、サポートについては、特定のコンパイラ オプションが必要です。

エラー **C2429: 言語機能 '入れ子になった名前空間の定義' コンパイラ フラグが必要 '/std:c:operator++ 17'** 定義しようとする場合に生成される、*複合名前空間*、1 つまたは複数を含む名前空間名前空間のスコープにネストされた名前、Visual Studio 2015 更新プログラム 5 以降します。 (Visual Studio 2017 15.3 のバージョンで、 **/std:c + + 最新**スイッチが必要です)。複合の名前空間の定義が、c++ 17 の前に C++ では許可されていません。 コンパイラは、複合名前空間の定義をサポートしているときに、 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
