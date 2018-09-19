---
title: コンパイラ エラー C3163 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e712a70bdd443d9a6c640853b958f29dac78dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061969"
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