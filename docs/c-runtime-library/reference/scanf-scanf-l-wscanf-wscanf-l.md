---
title: scanf、_scanf_l、wscanf、_wscanf_l
ms.date: 11/04/2016
apiname:
- _wscanf_l
- scanf
- _scanf_l
- wscanf
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
- _tscanf
- _scanf_l
- wscanf
- _wscanf_l
- scanf
- _tscanf_l
helpviewer_keywords:
- tscanf_l function
- _tscanf_l function
- reading data [C++], from input streams
- _tscanf function
- data [C++], reading from input stream
- scanf_l function
- scanf function
- wscanf function
- _scanf_l function
- tscanf function
- formatted data [C++], from input streams
- wscanf_l function
- _wscanf_l function
ms.assetid: 73eac607-117f-4be4-9ff0-4afd9cf3c848
ms.openlocfilehash: 48aa0bb3348a3336de9ee0eb9f9ec0d3e1a2b3cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544769"
---
# <a name="scanf-scanfl-wscanf-wscanfl"></a>scanf、_scanf_l、wscanf、_wscanf_l

標準入力ストリームから書式付きデータを読み取ります。 これらの関数のセキュリティを強化したバージョンを使用できます。「[scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int scanf(
   const char *format [,
   argument]...
);
int _scanf_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf(
   const wchar_t *format [,
   argument]...
);
int _wscanf_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>パラメーター

*format*<br/>
書式指定文字列。

*argument*<br/>
省略可能な引数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常に変換され、代入されたフィールドの数を返します。この数には、読み取られても代入されなかったフィールドは含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。

場合*形式*は、 **NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、 **EOF**設定と**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Scanf**関数は、標準入力ストリームからデータを読み取る**stdin**によって指定される場所にデータを書き込みます*引数*します。 各*引数*に型指定子に対応する型の変数へのポインターである必要があります*形式*します。 重なり合う文字列間でコピーした場合の動作は未定義です。

> [!IMPORTANT]
> 含む文字列を読み取るときに**scanf**の幅を常に指定、 **%s**形式 (たとえば、 **「% 男女」** の代わりに **"%s"**)、それ以外の適切な形式で入力には、バッファー オーバーランをなりやすいことができます。 代わりに、[scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) または [fgets](fgets-fgetws.md) を使用することをご検討ください。

**wscanf**のワイド文字バージョンです**scanf**、*形式*への引数**wscanf**はワイド文字列です。 **wscanf**と**scanf**ストリームが ANSI モードで開かれている場合の動作は同じです。 **scanf** UNICODE ストリームからの入力を現在サポートされていません。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf**|**scanf**|**scanf**|**wscanf**|
|**_tscanf_l**|**_scanf_l**|**_scanf_l**|**_wscanf_l**|

詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**scanf**、 **_scanf_l**|\<stdio.h>|
|**wscanf**、 **_wscanf_l**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_scanf.c
// compile with: /W3
// This program uses the scanf and wscanf functions
// to read formatted input.

#include <stdio.h>

int main( void )
{
   int   i, result;
   float fp;
   char  c, s[81];
   wchar_t wc, ws[81];
   result = scanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws ); // C4996
   // Note: scanf and wscanf are deprecated; consider using scanf_s and wscanf_s
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);
   result = wscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws ); // C4996
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);
}
```

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[fscanf、_fscanf_l、fwscanf、_fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
