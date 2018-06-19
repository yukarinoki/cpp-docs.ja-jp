---
title: strnlen、strnlen_s、wcsnlen、wcsnlen_s、_mbsnlen、_mbsnlen_l、_mbstrnlen、_mbstrnlen_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
dev_langs:
- C++
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22adcaafc54a6b086629b7b9087b7088001bba85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417759"
---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen、strnlen_s、wcsnlen、wcsnlen_s、_mbsnlen、_mbsnlen_l、_mbstrnlen、_mbstrnlen_l

現在のロケールまたは渡されたロケールを使用して、文字列の長さを取得します。 これらは、[strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md) のセキュリティを強化したバージョンです。

> [!IMPORTANT]
> **_mbsnlen**、 **_mbsnlen_l**、 **_mbstrnlen**、および **_mbstrnlen_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
NULL で終わる文字列。

*numberOfElements*<br/>
文字列バッファーのサイズ。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの関数は、文字列内の文字数を返します (終端の null 文字は含まれません)。 内の null ターミネータがない場合*numberOfElements*バイトの文字列 (またはワイド文字**wcsnlen**)、し*numberOfElements*に返されますエラー条件です。null で終わる文字列の長さは、厳密にであるより小さい*numberOfElements*です。

**_mbstrnlen**と **_mbstrnlen_l**文字列に無効なマルチバイト文字が含まれている場合、-1 を返します。

## <a name="remarks"></a>コメント

> [!NOTE]
> **strnlen**に代わるものではない**strlen**です。**strnlen**既知のサイズのバッファーに入力方向の信頼されていないデータのサイズを計算するためだけに使用するものでは、ネットワーク パケットなどです。 **strnlen**長さを計算しますが、文字列の終端がない場合、バッファーの末尾を越えた超えません。 その他の状況を使用して**strlen**です。 (同じ**wcsnlen**、 **_mbsnlen**、および **_mbstrnlen**)。

これらの各関数の文字数を返しますで*str*、終端の null 文字を含まない。 ただし、 **strnlen**と**strnlen_s** 1 バイト文字の文字列として文字列を解釈し、そのため、戻り値は常に (バイト単位) の数と等しく、文字列には、マルチバイトが含まれている場合でも文字があります。 **wcsnlen**と**wcsnlen_s**のワイド文字バージョンは、 **strnlen**と**strnlen_s**の引数をそれぞれ; **wcsnlen**と**wcsnlen_s**ワイド文字列であり、文字数はワイド文字単位で。 それ以外の場合、 **wcsnlen**と**strnlen**の動作は同じ、しないで**strnlen_s**と**wcsnlen_s**です。

**strnlen**、 **wcsnlen**、および **_mbsnlen**はそのパラメーターを検証しません。 場合*str*は**NULL**、アクセス違反が発生します。

**strnlen_s**と**wcsnlen_s**パラメーターを検証します。 場合*str*は**NULL**関数は、0 を返します。

**_mbstrnlen**もそのパラメーターを検証します。 場合*str*は**NULL**、または*numberOfElements*がより大きい**INT_MAX**、 **_mbstrnlen**」の説明に従って、無効なパラメーター例外を生成[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合 **_mbstrnlen**設定**errno**に**EINVAL**し、-1 を返します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen**と **_mbstrnlen**マルチバイト文字の文字列のマルチバイト文字の数を返します。 **_mbsnlen**のマルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識するが現在使用中かは、渡されたロケールに従って以外のマルチバイト文字の有効性テストは実行されません。 **_mbstrnlen**マルチバイト文字の有効性をテストし、マルチバイト文字のシーケンスを認識します。 場合に渡される文字列 **_mbstrnlen**に無効なマルチバイト文字を含む**errno**に設定されている**EILSEQ**です。

出力値の設定の影響を受けた、 **LC_CTYPE** 、ロケールのカテゴリの設定; 参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 いないする点を除いて、これらの関数のバージョンが同じである、 **_l**サフィックスは、このロケールに依存する動作と付いているバージョンの現在のロケールを使用して、 **_l**サフィックス代わりに渡されたロケール パラメーターを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strnlen**、 **strnlen_s**|\<string.h>|
|**wcsnlen**、 **wcsnlen_s**|\<string.h> または \<wchar.h>|
|**_mbsnlen**、 **_mbsnlen_l**|\<mbstring.h>|
|**_mbstrnlen**、 **_mbstrnlen_l**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
