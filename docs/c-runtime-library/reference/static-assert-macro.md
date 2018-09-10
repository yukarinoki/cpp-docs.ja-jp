---
title: _STATIC_ASSERT マクロ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _STATIC_ASSERT
dev_langs:
- C++
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8eda76666679b133b2d5486d21cd4c8e24d1fdf3
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105084"
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT マクロ

コンパイル時に式を評価し、結果がエラーを生成**FALSE**します。

## <a name="syntax"></a>構文

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
0 以外の値に評価される式 (ポインターを含む) (**TRUE**) または 0 (**FALSE**)。

## <a name="remarks"></a>Remarks

このマクロに似ています、 [_assert マクロと _ASSERTE マクロ](assert-asserte-assert-expr-macros.md)ことを除いて、*ブール式*は実行時ではなく、コンパイル時に評価されます。 場合*ブール式*に評価される**FALSE** (0)、[コンパイラ エラー C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md)が生成されます。

## <a name="example"></a>例

この例で確認かどうか、 [sizeof](../../c-language/sizeof-operator-c.md) 、 **int** 2 バイト以上かどうかおよび、 [sizeof](../../c-language/sizeof-operator-c.md) 、**長い**1 バイトします。 プログラムはコンパイルされずが生成されます[コンパイラ エラー C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md)ため、**長い**が 1 バイトを超えています。

```C
// crt__static_assert.c

#include <crtdbg.h>
#include <stdio.h>

_STATIC_ASSERT(sizeof(int) >= 2);
_STATIC_ASSERT(sizeof(long) == 1);  // C2466

int main()
{
    printf("I am sure that sizeof(int) will be >= 2: %d\n",
        sizeof(int));
    printf("I am not so sure that sizeof(long) == 1: %d\n",
        sizeof(long));
}
```

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-----------|---------------------|
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_ASSERT、_ASSERTE、_ASSERT_EXPR Macros](assert-asserte-assert-expr-macros.md)<br/>
