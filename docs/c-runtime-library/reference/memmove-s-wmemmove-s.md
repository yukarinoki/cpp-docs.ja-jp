---
title: memmove_s、wmemmove_s
ms.date: 4/2/2020
api_name:
- wmemmove_s
- memmove_s
- _o_wmemmove_s
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemmove_s
- memmove_s
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
ms.openlocfilehash: baec33046f891f64c04adeccf21f41d3eec7b814
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333152"
---
# <a name="memmove_s-wmemmove_s"></a>memmove_s、wmemmove_s

バッファーを別のバッファーに移動します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [memmove、wmemmove](memmove-wmemmove.md) です。

## <a name="syntax"></a>構文

```C
errno_t memmove_s(
   void *dest,
   size_t numberOfElements,
   const void *src,
   size_t count
);
errno_t wmemmove_s(
   wchar_t *dest,
   size_t numberOfElements,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
コピー先のオブジェクト。

*要素の数*<br/>
コピー先のバッファーのサイズ。

*src*<br/>
コピー元のオブジェクト。

*count*<br/>
コピーするバイト数 (**memmove_s**) または文字 (**wmemmove_s**) の数。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します

### <a name="error-conditions"></a>エラー条件

|*dest*|*要素の数*|*src*|戻り値|*デスト*の内容|
|------------|------------------------|-----------|------------------|------------------------|
|**NULL**|any|any|**Einval**|変更されない|
|any|any|**NULL**|**Einval**|変更されない|
|any|< *カウント*|any|**ERANGE**|変更されない|

## <a name="remarks"></a>解説

文字数*の*バイト数を*src*から*dest*にコピーします。 ソース領域とコピー先の領域の一部が重複している場合 **、memmove_s**は、オーバーラップ領域内の元のソース バイトが上書きされる前にコピーされることを確認します。

*dest*または*src*が null ポインターの場合、または変換先文字列が小さすぎる場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、これらの関数は**EINVAL**を返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**memmove_s**|\<string.h>|
|**wmemmove_s**|\<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_memmove_s.c
//
// The program demonstrates the
// memmove_s function which works as expected
// for moving overlapping regions.

#include <stdio.h>
#include <string.h>

int main()
{
   char str[] = "0123456789";

   printf("Before: %s\n", str);

   // Move six bytes from the start of the string
   // to a new position shifted by one byte. To protect against
   // buffer overrun, the secure version of memmove requires the
   // the length of the destination string to be specified.

   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);

   printf_s(" After: %s\n", str);
}
```

### <a name="output"></a>出力

```Output
Before: 0123456789
After: 0012345789
```

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy、wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy_s、wcscpy_s、_mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
