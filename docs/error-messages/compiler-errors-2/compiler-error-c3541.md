---
title: コンパイラ エラー C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 32926d0ef9343bad9ed73458e4d52d317b628109
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221043"
---
# <a name="compiler-error-c3541"></a>コンパイラ エラー C3541

' type ': typeid を ' auto ' を含む型に適用することはできません

指定子が含まれているため、 [typeid](../../extensions/typeid-cpp-component-extensions.md)演算子を指定された型に適用できません **`auto`** 。

## <a name="example"></a>例

次の例では、C3541 が生成されます。

```cpp
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
[/Zc: auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
