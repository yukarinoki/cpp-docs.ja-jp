---
description: '詳細情報: コンパイラの警告 (レベル 4) C4457'
title: コンパイラの警告 (レベル 4) C4457
ms.date: 11/04/2016
f1_keywords:
- C4457
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
ms.openlocfilehash: 8898189668eba95619e6bd0d0ccf1cb8ca3afdfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251415"
---
# <a name="compiler-warning-level-4-c4457"></a>コンパイラの警告 (レベル 4) C4457

> '*identifier*' を宣言すると、関数パラメーターが非表示になります

ローカルスコープの *識別子* の宣言によって、同じ名前の関数パラメーターの宣言が非表示になります。 この警告は、ローカルスコープ内の *識別子* への参照が、パラメーターではなく、ローカルに宣言されたバージョンに解決されることを知らせることができます。これは、意図したものではない場合があります。 この問題を解決するには、パラメーター名と競合しないローカル変数名を指定することをお勧めします。

## <a name="example"></a>例

次の例では、のパラメーター `x` とローカル変数の `x` 名前が同じであるため、C4457 が生成され `member_fn` ます。 この問題を解決するには、パラメーターとローカル変数に別の名前を使用します。

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
