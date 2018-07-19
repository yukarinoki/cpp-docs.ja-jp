---
title: __max | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __max
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
- max
- __max
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d223f4288ccf40646e8f560cec7243b7e8f9f649
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398420"
---
# <a name="max"></a>__max

プリプロセッサ マクロには、2 つの値のうち、大きい方を返します。

## <a name="syntax"></a>構文

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>パラメーター

*a*、 *b*<br/>
比較する数値型の値。

## <a name="return-value"></a>戻り値

**_ _max**引数のうち、大きい方を返します。

## <a name="remarks"></a>コメント

**_Max**マクロが 2 つの値を比較しより大きな 1 つの値を返します。 引数には、符号付きまたは符号なしのすべての数値データ型を指定できます。 引数と戻り値はともに同じデータ型である必要があります。

返される引数は、マクロが 2 回評価されます。 引数が式など、評価されるときに、その値を変更する場合、予期しない結果につながります`*p++`です。

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>例

詳細については、「[__min](min.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>