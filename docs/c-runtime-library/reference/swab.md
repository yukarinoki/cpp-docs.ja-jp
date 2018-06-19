---
title: _swab | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _swab
- stdlib/_swab
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
dev_langs:
- C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeedb217466262d8643a851b5f93cb9ac26fb0a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408446"
---
# <a name="swab"></a>_swab

バイトを交換します。

## <a name="syntax"></a>構文

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>パラメーター

*src*データをコピーし、スワップします。

*dest*スワップ データの格納場所。

*n*をコピーし、スワップのバイト数。

## <a name="return-value"></a>戻り値

**Swab**関数が値を返しません。 関数のセットを**errno**に**EINVAL**いずれか、 *src*または*dest*ポインターが null または*n*が小さい無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

戻り値の詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

場合*n*が偶数の **_swab**関数のコピー *n*からバイト*src*、隣接する (バイト単位) の各ペアを交換およびで結果を格納*dest*です。 場合*n*が奇数 **_swab**をコピーし、最初の交換*n*-1 バイトまでの*src*と最後のバイトはコピーされません。 **_Swab**関数は、通常、異なるバイト順を使用するマシンに転送するためのバイナリ データを準備するのに使用します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> または \<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
