---
title: _memicmp、_memicmp_l
ms.date: 11/04/2016
apiname:
- _memicmp_l
- _memicmp
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _memicmp
- memicmp_l
- _memicmp_l
helpviewer_keywords:
- memicmp function
- _memicmp function
- memicmp_l function
- _memicmp_l function
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
ms.openlocfilehash: 8beb632c8bd2cfac486fc58fc930b94490bdecbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636814"
---
# <a name="memicmp-memicmpl"></a>_memicmp、_memicmp_l

2 つのバッファーの文字を比較します (大文字と小文字を区別しない)。

## <a name="syntax"></a>構文

```C
int _memicmp(
   const void *buffer1,
   const void *buffer2,
   size_t count
);
int _memicmp_l(
   const void *buffer1,
   const void *buffer2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*buffer1*<br/>
最初のバッファー。

*buffer2*<br/>
2 番目のバッファー。

*count*<br/>
文字数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

戻り値は、バッファー間の関係を示しています。

|戻り値|buf1 と buf2 の最初の count バイトの関係|
|------------------|--------------------------------------------------------|
|< 0|*buffer1*未満*buffer2*します。|
|0|*buffer1*と同じ*buffer2*します。|
|> 0|*buffer1*より大きい*buffer2*します。|
|**すると**|エラーが発生しました。|

## <a name="remarks"></a>Remarks

**_Memicmp**関数では、1 つ目を比較します。*カウント*2 つのバッファーの文字*buffer1*と*buffer2*バイトごと。 比較では、大文字と小文字を区別しません。

いずれか*buffer1*または*buffer2* null ポインターの場合は、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、関数を返します**すると**設定と**errno**に**EINVAL**します。

**_memicmp**ロケールに依存する動作に現在のロケールを使用 **_memicmp_l**代わりに渡されたロケールを使用すると同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_memicmp**|\<memory.h> または \<string.h>|
|**_memicmp_l**|\<memory.h> または \<string.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_memicmp.c
// This program uses _memicmp to compare
// the first 29 letters of the strings named first and
// second without regard to the case of the letters.

#include <memory.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   int result;
   char first[] = "Those Who Will Not Learn from History";
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";
   // Note that the 29th character is right here ^

   printf( "Compare '%.29s' to '%.29s'\n", first, second );
   result = _memicmp( first, second, 29 );
   if( result < 0 )
      printf( "First is less than second.\n" );
   else if( result == 0 )
      printf( "First is equal to second.\n" );
   else if( result > 0 )
      printf( "First is greater than second.\n" );
}
```

```Output
Compare 'Those Who Will Not Learn from' to 'THOSE WHO WILL NOT LEARN FROM'
First is equal to second.
```

## <a name="see-also"></a>関連項目

[バッファー操作](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr、wmemchr](memchr-wmemchr.md)<br/>
[memcmp、wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy、wmemcpy](memcpy-wmemcpy.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
