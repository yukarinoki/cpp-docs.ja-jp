---
title: strcpy_s、wcscpy_s、_mbscpy_s | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2086
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcscpy_s
- _mbscpy_s
- strcpy_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strcpy_s
- _mbscpy_s
- _tcscpy_s
- wcscpy_s
dev_langs:
- C++
helpviewer_keywords:
- strcpy_s function
- _tcscpy_s function
- _mbscpy_s function
- copying strings
- strings [C++], copying
- tcscpy_s function
- wcscpy_s function
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee648776d4c8b7df1089edf34d30b5c7e59a63c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416613"
---
# <a name="strcpys-wcscpys-mbscpys"></a>strcpy_s、wcscpy_s、_mbscpy_s

文字列をコピーします。 これらのバージョンの [strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されました。

> [!IMPORTANT]
> **_mbscpy_s** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t strcpy_s(
   char *dest,
   rsize_t dest_size,
   const char *src
);
errno_t wcscpy_s(
   wchar_t *dest,
   rsize_t dest_size,
   const wchar_t *src
);
errno_t _mbscpy_s(
   unsigned char *dest,
   rsize_t dest_size,
   const unsigned char *src
);
```

```cpp
// Template functions are C++ only:
template <size_t size>
errno_t strcpy_s(
   char (&dest)[size],
   const char *src
); // C++ only
template <size_t size>
errno_t wcscpy_s(
   wchar_t (&dest)[size],
   const wchar_t *src
); // C++ only
template <size_t size>
errno_t _mbscpy_s(
   unsigned char (&dest)[size],
   const unsigned char *src
); // C++ only
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
追加先の文字列バッファーの場所。

*dest_size*<br/>
移行先の文字列バッファーのサイズ**char**ナローとマルチバイト関数では、ユニットと**wchar_t**ワイド関数の単位。 この値は 0 より大きい値より大きくしたりする必要があります**RSIZE_MAX**です。

*src*<br/>
null で終わる元の文字列バッファー。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラーを返します。

### <a name="error-conditions"></a>エラー条件

|*dest*|*dest_size*|*src*|戻り値|内容*dest*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL**|任意|任意|**EINVAL**|変更されない|
|任意|任意|**NULL**|**EINVAL**|*dest*を 0 に [0] の設定|
|任意|0 または小さすぎる|任意|**ERANGE**|*dest*を 0 に [0] の設定|

## <a name="remarks"></a>コメント

**Strcpy_s**関数のアドレスの内容をコピーする*src*で指定されている場所に、終端の null 文字を含む*dest*です。 コピー先の文字列には、コピー元の文字列とその終端の NULL 文字を保持できるサイズが必要です。 動作**strcpy_s**元とコピー先文字列が重なり合っている場合に定義されていません。

**wcscpy_s**のワイド文字バージョンは、 **strcpy_s**、および **_mbscpy_s**マルチバイト文字バージョンです。 引数**wcscpy_s**ワイド文字は、文字列以外の **_mbscpy_s**マルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。

場合*dest*または*src*が null ポインターの場合は、移行先の文字列のサイズまたは*dest_size*小さすぎる、無効なパラメーター ハンドラーが呼び出される、 」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、 **EINVAL**設定と**errno**に**EINVAL**とき*dest*または*src* null ポインターでは、返される**ERANGE**設定と**errno**に**ERANGE**コピー先文字列が小さすぎる場合です。

正常に実行されると、コピー先の文字列は常に NULL で終わります。

C++ では、これらの関数をより簡単に使用できます。これはバッファー長を自動的に推論できるテンプレートのオーバーロードにより可能です。その結果、サイズの引数を指定する必要がなくなります。また、セキュリティが万全ではない以前の関数は、セキュリティが強化された新しい関数に自動的に置き換わります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリのバージョンは、最初にバッファーを 0 xfe でを入力します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).を使用します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscpy_s**|**strcpy_s**|**_mbscpy_s**|**wcscpy_s**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strcpy_s**|\<string.h>|
|**wcscpy_s**|\<string.h> または \<wchar.h>|
|**_mbscpy_s**|\<mbstring.h>|

これらの関数は、Microsoft 固有です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

実稼働品質のコードは、このサンプルは、エラーをチェックせず、セキュリティで保護された文字列関数を呼び出します。

```C
// crt_strcpy_s.c
// Compile by using: cl /W4 crt_strcpy_s.c
// This program uses strcpy_s and strcat_s
// to build a phrase.

#include <string.h>     // for strcpy_s, strcat_s
#include <stdlib.h>     // for _countof
#include <stdio.h>      // for printf
#include <errno.h>      // for return values

int main(void)
{
    char string[80];

    strcpy_s(string, _countof(string), "Hello world from ");
    strcat_s(string, _countof(string), "strcpy_s ");
    strcat_s(string, _countof(string), "and ");
    strcat_s(string, _countof(string), "strcat_s!");

    printf("String = %s\n", string);
}
```

```Output
String = Hello world from strcpy_s and strcat_s!
```

C++ コードを作成するときにテンプレートのバージョンが使いやすい場合があります。

```cpp
// crt_wcscpy_s.cpp
// Compile by using: cl /EHsc /W4 crt_wcscpy_s.cpp
// This program uses wcscpy_s and wcscat_s
// to build a phrase.

#include <cstring>  // for wcscpy_s, wcscat_s
#include <cstdlib>  // for _countof
#include <iostream> // for cout, includes <cstdlib>, <cstring>
#include <errno.h>  // for return values

int main(void)
{
    wchar_t string[80];
    // using template versions of wcscpy_s and wcscat_s:
    wcscpy_s(string, L"Hello world from ");
    wcscat_s(string, L"wcscpy_s ");
    wcscat_s(string, L"and ");
    // of course we can supply the size explicitly if we want to:
    wcscat_s(string, _countof(string), L"wcscat_s!");

    std::wcout << L"String = " << string << std::endl;
}
```

```Output
String = Hello world from wcscpy_s and wcscat_s!
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat、wcscat、_mbscat](strcat-wcscat-mbscat.md) <br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s、_strncat_s_l、wcsncat_s、_wcsncat_s_l、_mbsncat_s、_mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
