---
description: '詳細情報: コンパイラの警告 (レベル 4) C4456'
title: コンパイラの警告 (レベル 4) C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: f066de07b0c6bf7a7b5de3143909e402b0fedde3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241314"
---
# <a name="compiler-warning-level-4-c4456"></a>コンパイラの警告 (レベル 4) C4456

> '*identifier*' を宣言すると、以前のローカル宣言が非表示になります

ローカルスコープの *識別子* の宣言により、同じ名前の前のローカル宣言の宣言が非表示になります。 この警告は、ローカルスコープ内の *識別子* への参照が、以前のローカルではなく、ローカルで宣言されたバージョンに解決されることを知らせます。これは意図したものではない場合があります。 この問題を解決するには、他のローカル名と競合しないローカル変数名を指定することをお勧めします。

## <a name="example"></a>例

次の例では、の loop コントロール変数 `int x` とローカル変数の `double x` 名前が同じであるため、C4456 が生成され `member_fn` ます。 この問題を解決するには、ローカル変数に別の名前を使用します。

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
