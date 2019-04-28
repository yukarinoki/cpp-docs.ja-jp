---
title: コンパイラ エラー C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: eda3910c99f4c8ea96568f2d475c5d6a1e4cdc7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174226"
---
# <a name="compiler-error-c3163"></a>コンパイラ エラー C3163

'construct': 前の宣言と一貫性のない属性

定義に適用される属性は、宣言に適用される属性と競合します。

C3163 を解決するのには 1 つの方法では、事前宣言で属性を除外します。 事前宣言で属性が定義の属性よりも小さくする以上で、多くて、それらに。

C3163 エラーの考えられる原因には、Microsoft ソース コード注釈言語 (SAL) が含まれます。 使用してプロジェクトをコンパイルするまで、SAL マクロは展開されません、 **/analyze**フラグ。 /Analyze せず、正常にコンパイルされるプログラムを再コンパイルしようとした場合、C3163 がスロー、/analyze オプション。 SAL については、次を参照してください。 [SAL 注釈](../../c-runtime-library/sal-annotations.md)します。

## <a name="example"></a>例

次の例では、C3163 が生成されます。

```
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