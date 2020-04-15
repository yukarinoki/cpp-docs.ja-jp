---
title: memcpy_s、wmemcpy_s
ms.date: 4/2/2020
api_name:
- memcpy_s
- wmemcpy_s
- _o_memcpy_s
- _o_wmemcpy_s
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
- wmemcpy_s
- memcpy_s
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
ms.openlocfilehash: dc5e49115b65b6883e55df13d0610231a87c1c55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333335"
---
# <a name="memcpy_s-wmemcpy_s"></a>memcpy_s、wmemcpy_s

バッファー間でバイトをコピーします。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [memcpy、wmemcpy](memcpy-wmemcpy.md) です。

## <a name="syntax"></a>構文

```C
errno_t memcpy_s(
   void *dest,
   size_t destSize,
   const void *src,
   size_t count
);
errno_t wmemcpy_s(
   wchar_t *dest,
   size_t destSize,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
コピー先のバッファー。

*デストサイズ*<br/>
コピー先バッファーのサイズ。memcpy_s の場合はバイト単位、wmemcpy_s の場合はワイド文字列 (wchar_t) 単位です。

*src*<br/>
コピー元のバッファー。

*count*<br/>
コピーする文字数。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*dest*|*デストサイズ*|*src*|*count*|戻り値|*デスト*の内容|
|------------|----------------|-----------|---|------------------|------------------------|
|any|any|any|0|0|変更されない|
|**NULL**|any|any|0 以外|**Einval**|変更されない|
|any|any|**NULL**|0 以外|**Einval**|*dest*がゼロに設定されている|
|any|< *カウント*|any|0 以外|**ERANGE**|*dest*がゼロに設定されている|

## <a name="remarks"></a>解説

**memcpy_s**は *、カウント*バイトを*src*から*dest*にコピーします。**コピーwmemcpy_s**は、ワイド文字 (2 バイト) を*カウント*します。 ソースと宛先が重複している場合 **、memcpy_s**の動作は未定義です。 memmove_s**を使用**して、重複する領域を処理します。

これらの関数では、パラメーターの検証が行われます。 *count*が 0 以外*で、dest*または*drc*が null ポインターである場合、または*destSize*が*count*より小さい場合、これらの関数は、パラメーター[の検証](../../c-runtime-library/parameter-validation.md)で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、これらの関数は**EINVAL**または**ERANGE**を戻し **、errno**を戻り値に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> または \<string.h>|
|**wmemcpy_s**|\<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_memcpy_s.c
// Copy memory in a more secure way.

#include <memory.h>
#include <stdio.h>

int main()
{
   int a1[10], a2[100], i;
   errno_t err;

   // Populate a2 with squares of integers
   for (i = 0; i < 100; i++)
   {
      a2[i] = i*i;
   }

   // Tell memcpy_s to copy 10 ints (40 bytes), giving
   // the size of the a1 array (also 40 bytes).
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );
   if (err)
   {
      printf("Error executing memcpy_s.\n");
   }
   else
   {
     for (i = 0; i < 10; i++)
       printf("%d ", a1[i]);
   }
   printf("\n");
}
```

```Output
0 1 4 9 16 25 36 49 64 81
```

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr、wmemchr](memchr-wmemchr.md)<br/>
[memcmp、wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove、wmemmove](memmove-wmemmove.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
