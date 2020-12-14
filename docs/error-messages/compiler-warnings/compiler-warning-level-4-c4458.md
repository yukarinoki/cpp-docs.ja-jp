---
description: '詳細情報: コンパイラの警告 (レベル 4) C4458'
title: コンパイラの警告 (レベル 4) C4458
ms.date: 11/04/2016
f1_keywords:
- C4458
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
ms.openlocfilehash: f631fe4086c69732c972161ae7bb6096232b2740
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241262"
---
# <a name="compiler-warning-level-4-c4458"></a>コンパイラの警告 (レベル 4) C4458

> '*identifier*' の宣言はクラスメンバーを非表示にします

ローカルスコープの *識別子* の宣言によって、クラススコープで同じ名前の *識別子* の宣言が非表示になります。 この警告は、このスコープ内の *識別子* への参照が、クラスメンバーバージョンではなく、ローカルで宣言されたバージョンに解決されることを知らせることができます。これは意図したものではない場合があります。 この問題を解決するには、クラスメンバー名と競合しないローカル変数名を指定することをお勧めします。

## <a name="example"></a>例

次の例では、のパラメーター `x` とローカル変数の `y` `member_fn` 名前がクラスのデータメンバーと同じであるため、C4458 が生成されます。 この問題を解決するには、パラメーターとローカル変数に別の名前を使用します。

```cpp
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;
        // To fix this issue, change the parameter name x
        // and local name y to something that does not
        // conflict with the data member names.
    }
} s;
```
