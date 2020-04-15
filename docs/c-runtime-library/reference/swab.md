---
title: _swab
ms.date: 4/2/2020
api_name:
- _swab
- stdlib/_swab
- _o__swab
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: f7fe23cd9c1b2eab52ebe50904d0bb18fe16cea6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362962"
---
# <a name="_swab"></a>_swab

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

*src*<br/>
コピーおよび交換されるデータ。

*dest*<br/>
交換したデータの格納場所。

*n*<br/>
コピーおよび交換対象のバイト数。

## <a name="return-value"></a>戻り値

**swab**関数は値を返しません。 src または*dest*ポインターのいずれかが null*src*または*n*未満の場合、関数は**errno**を**EINVAL**に設定し、無効なパラメーター ハンドラーが呼び出されます。."[パラメーターの検証](../../c-runtime-library/parameter-validation.md)に示すようにします。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

*n*が偶数の場合 **、_swab**関数は*src*から*n*バイトをコピーし、隣接するバイトの各ペアをスワップして、結果を*dest*に格納します。 *n*が奇数の場合 **、_swab** *src*の最初の*n*-1 バイトをコピーしてスワップし、最後のバイトはコピーされません。 **_swab**関数は、通常、異なるバイトオーダーを使用するマシンに転送するためのバイナリデータを準備するために使用されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> または \<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
