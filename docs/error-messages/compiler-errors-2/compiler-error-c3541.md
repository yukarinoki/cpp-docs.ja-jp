---
title: コンパイラ エラー C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 356936ee09b75b6930840e015d00ccebb2fd8bc2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596379"
---
# <a name="compiler-error-c3541"></a>コンパイラ エラー C3541

'type': 'auto' を含む型に typeid は適用できません

[Typeid](../../windows/typeid-cpp-component-extensions.md)演算子を含んでいるため、示された型には適用できません、`auto`指定子。

## <a name="example"></a>例

次の例では、C3541 を生成します。

```
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../windows/typeid-cpp-component-extensions.md)