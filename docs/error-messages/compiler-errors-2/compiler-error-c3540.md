---
title: コンパイラ エラー C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 57e4145557272f76a890a356c79982346cd74d7e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037170"
---
# <a name="compiler-error-c3540"></a>コンパイラ エラー C3540

'type': 'auto' を含む型に sizeof は適用できません

[Sizeof](../../cpp/sizeof-operator.md)演算子を含んでいるため、示された型には適用できません、`auto`指定子。

## <a name="example"></a>例

次の例では、C3540 を生成します。

```
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

[auto キーワード](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof 演算子](../../cpp/sizeof-operator.md)