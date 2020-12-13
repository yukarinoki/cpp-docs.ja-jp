---
description: '詳細については、「方法: _Analysis_assume を使用して追加のコード情報を指定する」を参照してください。'
title: コード分析ヒントに _Analysis_assume を使用する
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
ms.openlocfilehash: 1960fae929f1bd0ffbac4979b76541fd0d396e42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151555"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume"></a>方法: _Analysis_assume を使用して追加のコード情報を指定する

C/c + + コードのコード分析ツールにヒントを提供して、分析プロセスを支援し、警告を減らすことができます。 追加情報を提供するには、次の関数を使用します。

`_Analysis_assume(`  `expr`  `)`

`expr` -true として評価されることを前提とする任意の式。

コード分析ツールでは、式によって表される条件が、関数が出現する位置で true であることを前提としています。また、変数への代入などによって、式が変更されるまでは true のままです。

> [!NOTE]
> `_Analysis_assume` コードの最適化には影響しません。 コード分析ツールの外部で `_Analysis_assume` は、は非 op として定義されます。

## <a name="example"></a>例

次のコードでは、を使用して `_Analysis_assume` 、コード分析の警告 [C6388](../code-quality/c6388.md)を修正します。

```cpp
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>関連項目

- [__assume](../intrinsics/assume.md)
