---
description: 詳細については、 _Analysis_assume_ を使用して追加のコード情報を指定する方法に関するページを参照してください。
title: コード分析ヒントに _Analysis_assume_ を使用する
ms.date: 12/16/2020
ms.topic: conceptual
f1_keywords:
- _Analysis_assume_
helpviewer_keywords:
- _Analysis_assume_
ms.openlocfilehash: f4244a896d4334cb6c5e857e63b39be0cd53b08b
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645125"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume_"></a>を使用して追加のコード情報を指定する方法 `_Analysis_assume_`

C/c + + コードのコード分析ツールにヒントを提供して、分析プロセスを支援し、警告を減らすことができます。 追加情報を提供するには、次の関数マクロを使用します。

`_Analysis_assume( expr )`

*`expr`* -true として評価されることを前提とする任意の式。

コード分析ツールは、式によって表される条件が、関数が出現する位置で true であることを前提としてい *`expr`* ます。 また、 *`expr`* が変更されるまで (たとえば、変数への代入によって)、true のままです。

> [!NOTE]
> `_Analysis_assume_` コードの最適化には影響しません。 コード分析ツールの外部で `_Analysis_assume_` は、は非 op として定義されます。

## <a name="example"></a>例

次のコードでは、を使用して `_Analysis_assume_` 、コード分析の警告 [C6388](../code-quality/c6388.md)を修正します。

```cpp
#include <windows.h>
#include <codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume_(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>関連項目

- [__assume](../intrinsics/assume.md)
