---
title: コンパイラ エラー C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 897defd5643a90234c2ae3b7bb4f58904864e858
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508083"
---
# <a name="compiler-error-c3540"></a>コンパイラ エラー C3540

' type ': sizeof を ' auto ' を含む型に適用することはできません

指定された型には指定子が含まれているため、 [sizeof](../../cpp/sizeof-operator.md) 演算子を適用することはできません **`auto`** 。

## <a name="example"></a>例

次の例では、C3540 が生成されます。

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-cpp.md)<br/>
[/Zc: auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof 演算子](../../cpp/sizeof-operator.md)
