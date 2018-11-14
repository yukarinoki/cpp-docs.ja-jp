---
title: vscanf、vwscanf
ms.date: 11/04/2016
apiname:
- vscanf
- vwscanf
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
- vscanf
- vwscanf
- _vtscanf
ms.assetid: d1df595b-11bc-4682-9441-a92616301e3b
ms.openlocfilehash: 936dcc34fb0d2ed73919ca59c7419f2090c54e28
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519257"
---
# <a name="vscanf-vwscanf"></a>vscanf、vwscanf

標準入力ストリームから書式付きデータを読み取ります。 これらの関数のセキュリティを強化したバージョンについては、「[vscanf_s、vwscanf_s](vscanf-s-vwscanf-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int vscanf(
   const char *format,
   va_list arglist
);
int vwscanf(
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>パラメーター

*format*<br/>
書式指定文字列。

*arglist*<br/>
可変個引数リスト。

## <a name="return-value"></a>戻り値

正常に変換され、代入されたフィールドの数を返します。この数には、読み取られても代入されなかったフィールドは含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。

場合*形式*は、 **NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、 **EOF**設定と**errno**に**EINVAL**します。

エラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Vscanf**関数は、標準入力ストリームからデータを読み取る**stdin**で指定されている場所にデータを書き込みます、 *arglist*引数リスト。 リスト内の各引数は型指定子に対応する型の変数へのポインターである必要があります*形式*します。 重なり合う文字列間でコピーした場合の動作は未定義です。

> [!IMPORTANT]
> 使用すると**vscanf**の幅を常に文字列を読み取り、指定、 **%s**形式 (たとえば、 **「% 男女」** の代わりに **"%s"**);それ以外の場合、正しくない形式の入力には、バッファー オーバーランを可能性があります。 代わりに、[vscanf_s、vwscanf_s](vscanf-s-vwscanf-s.md) または [fgets](fgets-fgetws.md) を使用できます。

**vwscanf**のワイド文字バージョンです**vscanf**、*形式*引数**vwscanf**はワイド文字列です。 **vwscanf**と**vscanf**ストリームが ANSI モードで開かれている場合の動作は同じです。 **vscanf** UNICODE ストリームからの入力をサポートしていません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf**|**vscanf**|**vscanf**|**vwscanf**|

詳細については、「[Format Specification Fields: scanf and wscanf Functions](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」(scanf 関数と wscanf 関数の書式指定フィールド) をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**vscanf**|\<stdio.h>|
|**vwscanf**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_vscanf.c
// compile with: /W3
// This program uses the vscanf and vwscanf functions
// to read formatted input.

#include <stdio.h>
#include <stdarg.h>

int call_vscanf(char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vscanf(format, arglist);
    va_end(arglist);
    return result;
}

int call_vwscanf(wchar_t *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vwscanf(format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    int   i, result;
    float fp;
    char  c, s[81];
    wchar_t wc, ws[81];
    result = call_vscanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws );
    printf( "The number of fields input is %d\n", result );
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);
    result = call_vwscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws );
    wprintf( L"The number of fields input is %d\n", result );
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);
}
```

```Output

      71 98.6 h z Byte characters
36 92.3 y n Wide charactersThe number of fields input is 6
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
[vscanf_s、vwscanf_s](vscanf-s-vwscanf-s.md)<br/>
