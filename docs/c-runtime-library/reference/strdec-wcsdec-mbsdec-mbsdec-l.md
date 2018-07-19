---
title: _strdec、_wcsdec、_mbsdec、_mbsdec_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
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
apitype: DLLExport
f1_keywords:
- _strdec
- mbsdec_l
- strdec
- _mbsdec
- _mbsdec_l
- mbsdec
- wcsdec
- _wcsdec
dev_langs:
- C++
helpviewer_keywords:
- mbsdec_l function
- mbsdec function
- tcsdec function
- _tcsdec function
- _strdec function
- _wcsdec function
- _mbsdec_l function
- strdec function
- wcsdec function
- _mbsdec function
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c73813c406011eaadd540398d3364ec183f8deaf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414218"
---
# <a name="strdec-wcsdec-mbsdec-mbsdecl"></a>_strdec、_wcsdec、_mbsdec、_mbsdec_l

文字列ポインターを 1 文字前へ移動します。

> [!IMPORTANT]
> **mbsdec**と**mbsdec_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned char *_strdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned wchar_t *_wcsdec(
   const unsigned wchar_t *start,
   const unsigned wchar_t *current
);
unsigned char *_mbsdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned char *_mbsdec_l(
   const unsigned char *start,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*start*<br/>
任意の文字へのポインター (または **_mbsdec**と **_mbsdec_l**、任意のマルチバイト文字の最初のバイト) 元の文字列です。*開始*前に指定する必要があります*現在*元の文字列。

*current*<br/>
任意の文字へのポインター (または **_mbsdec**と **_mbsdec_l**、任意のマルチバイト文字の最初のバイト) 元の文字列です。*現在*従う必要があります*開始*元の文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsdec**、 **_mbsdec_l**、 **_strdec**、および **_wcsdec**直前にある文字へのポインターを返す各*現在*;**_mbsdec**返します**NULL**場合の値*開始*以上のものには、*現在*です。 **_tcsdec**これらの関数と戻り値のいずれかにマップが異なります。

## <a name="remarks"></a>コメント

**_Mbsdec**と **_mbsdec_l**関数では、ポインターを返す前に記述するマルチバイト文字の最初のバイトまで*現在*を含む文字列*開始*です。

出力値の設定の影響を受けた、 **LC_CTYPE** 、ロケールのカテゴリの設定; 参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。  **_mbsdec** 、使用されているロケールに従ってマルチバイト文字シーケンスを認識中に **_mbsdec_l**に渡されたロケール パラメーターを代わりに使用する点を除いてと同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*開始*または*現在*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、この関数を返します**EINVAL**設定と**errno**に**EINVAL**です。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsdec**|**_strdec**|**_mbsdec**|**_wcsdec**|

**_strdec**と **_wcsdec**の 1 バイト文字とワイド文字バージョンは、 **_mbsdec**と **_mbsdec_l**です。 **_strdec**と **_wcsdec**この割り当てにのみ提供され、それ以外の場合は使用できません。

詳細については、「[Using Generic-Text Mappings](../../c-runtime-library/using-generic-text-mappings.md)」(汎用テキスト マップの使用) および「[Generic-Text Mappings](../../c-runtime-library/generic-text-mappings.md)」(汎用テキスト マップ) をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbsdec**|\<mbstring.h>|\<mbctype.h>|
|**_mbsdec_l**|\<mbstring.h>|\<mbctype.h>|
|**_strdec**|\<tchar.h>||
|**_wcsdec**|\<tchar.h>||

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

次の例を使用して **_tcsdec**です。

```cpp
// crt_tcsdec.cpp
// Compile by using: cl /EHsc crt_tcsdec.cpp
#include <iostream>
#include <tchar.h>
using namespace std;

int main()
{
   const TCHAR *str = _T("12345");
   cout << "str: " << str << endl;

   const TCHAR *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   TCHAR *answer;
   answer = _tcsdec( str, str2 );
   cout << "answer: " << answer << endl;

   return (0);
}
```

次の例を使用して **_mbsdec**です。

```cpp
// crt_mbsdec.cpp
// Compile by using: cl /EHsc crt_mbsdec.c
#include <iostream>
#include <mbstring.h>
using namespace std;

int main()
{
   char *str = "12345";
   cout << "str: " << str << endl;

   char *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   unsigned char *answer;
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));

   cout << "answer: " << answer << endl;

   return (0);
}
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strinc、_wcsinc、_mbsinc、_mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc、_wcsnextc、_mbsnextc、_mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc、_wcsninc、_mbsninc、_mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
