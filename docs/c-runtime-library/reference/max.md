---
description: '詳細については、次を参照してください: __max'
title: __max
ms.date: 04/05/2018
api_name:
- __max
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- max
- __max
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
ms.openlocfilehash: 709bbb7aee48e65fdd3feb21eb1984135faae2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299651"
---
# <a name="__max"></a>__max

2つの値のうち、大きい方を返すプリプロセッサマクロ。

## <a name="syntax"></a>構文

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>パラメーター

*a*、 *b*<br/>
比較する数値型の値。

## <a name="return-value"></a>戻り値

**__max** は、その引数の大部分を返します。

## <a name="remarks"></a>解説

**__Max** マクロは、2つの値を比較し、大きい方の値を返します。 引数には、符号付きまたは符号なしのすべての数値データ型を指定できます。 引数と戻り値はともに同じデータ型である必要があります。

返される引数はマクロによって2回評価されます。 このため、引数が評価時に値を変更する式 (など) の場合、予期しない結果になる可能性が `*p++` あります。

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>例

詳細については、「[__min](min.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>
