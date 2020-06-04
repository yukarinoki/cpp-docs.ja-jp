---
title: _strdup、_wcsdup、_mbsdup
ms.date: 4/2/2020
api_name:
- _strdup
- _mbsdup
- _wcsdup
- _o__strdup
- _o__wcsdup
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
ms.openlocfilehash: 42b4a890c1c7f350b83bb92a548d716ee6d9ebfc
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914468"
---
# <a name="_strdup-_wcsdup-_mbsdup"></a>_strdup、_wcsdup、_mbsdup

文字列を複製します。

> [!IMPORTANT]
> **_mbsdup**は、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォームアプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *_strdup(
   const char *strSource
);
wchar_t *_wcsdup(
   const wchar_t *strSource
);
unsigned char *_mbsdup(
   const unsigned char *strSource
);
```

### <a name="parameters"></a>パラメーター

*strSource*<br/>
NULL で終わる元の文字列。

## <a name="return-value"></a>戻り値

これらの各関数は、コピーされた文字列の格納場所へのポインターを返すか、ストレージを割り当てることができない場合は**NULL**を返します。

## <a name="remarks"></a>解説

**_Strdup**関数は、 [malloc](malloc.md)を呼び出して、 *strsource*のコピーにストレージ領域を割り当ててから、 *strsource*を割り当てられた領域にコピーします。

**_wcsdup**と **_mbsdup**は **_strdup**のワイド文字バージョンとマルチバイト文字バージョンです。 **_Wcsdup**の引数と戻り値はワイド文字列です。これらの **_mbsdup**はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup**|**_strdup**|**_mbsdup**|**_wcsdup**|

**_Strdup**は**malloc**を呼び出して*strsource*のコピーにストレージ領域を割り当てます。そのため、 **_strdup**への呼び出しによって返されたポインターに対して[フリー](free.md)ルーチンを呼び出すことによって、常にこのメモリを解放することをお勧めします。

**_DEBUG**と **_CRTDBG_MAP_ALLOC**が定義されている場合、 **_strdup**と **_wcsdup**は、メモリ割り当てのデバッグを可能にするために **_strdup_dbg**と **_wcsdup_dbg**の呼び出しに置き換えられます。 詳細については、「[_strdup_dbg、_wcsdup_dbg](strdup-dbg-wcsdup-dbg.md)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_strdup**|\<string.h>|
|**_wcsdup**|\<string.h> または \<wchar.h>|
|**_mbsdup**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strdup.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is the buffer text";
   char *newstring;
   printf( "Original: %s\n", buffer );
   newstring = _strdup( buffer );
   printf( "Copy:     %s\n", newstring );
   free( newstring );
}
```

```Output
Original: This is the buffer text
Copy:     This is the buffer text
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memset、wmemset](memset-wmemset.md)<br/>
[strcat、wcscat、_mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
