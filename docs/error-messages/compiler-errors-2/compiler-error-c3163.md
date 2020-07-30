---
title: コンパイラ エラー C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 29f810ab1ab1608ab9c0492c9f88b8edfe042168
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87390027"
---
# <a name="compiler-error-c3163"></a>コンパイラ エラー C3163

> '*construct*': 属性が前の宣言と矛盾しています。

定義に適用されている属性が、宣言に適用されている属性と競合しています。

C3163 を解決する方法の1つは、事前宣言の属性を除外することです。 事前宣言の属性は、定義の属性よりも小さい値であるか、またはそれと同じである必要があります。

C3163 エラーの原因として、Microsoft ソースコード注釈言語 (SAL) が考えられます。 フラグを使用してプロジェクトをコンパイルしない限り、SAL マクロは展開されません **`/analyze`** 。 オプションを使用して再コンパイルしようとすると、を使用せずにクリーンにコンパイルされるプログラムでは、 **`/analyze`** C3163 がスローされる可能性があり **`/analyze`** ます。 SAL の詳細については、「 [Sal 注釈](../../c-runtime-library/sal-annotations.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3163 が生成されます。

```cpp
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>関連項目

[SAL 注釈](../../c-runtime-library/sal-annotations.md)
