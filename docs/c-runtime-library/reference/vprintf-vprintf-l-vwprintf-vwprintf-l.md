---
title: vprintf、_vprintf_l、vwprintf、_vwprintf_l
ms.date: 11/04/2016
apiname:
- vprintf
- _vwprintf_l
- _vprintf_l
- vwprintf
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
- vwprintf
- _vtprintf
helpviewer_keywords:
- vwprintf function
- _vwprintf_l function
- vwprintf_l function
- _vtprintf function
- vtprintf_l function
- vprintf function
- _vprintf_l function
- vprintf_l function
- vtprintf function
- _vtprintf_l function
- formatted text [C++]
ms.assetid: 44549505-00a0-4fa7-9a85-f2e666f55a38
ms.openlocfilehash: 18684484db33faffc581f30e39ef42e5356b71ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632727"
---
# <a name="vprintf-vprintfl-vwprintf-vwprintfl"></a>vprintf、_vprintf_l、vwprintf、_vwprintf_l

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらの関数のセキュリティを強化したバージョンを使用できます。「[vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l](vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int vprintf(
   const char *format,
   va_list argptr
);
int _vprintf_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int vwprintf(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>パラメーター

*format*<br/>
書式の指定。

*定義されています*<br/>
引数リストへのポインター。

*locale*<br/>
使用するロケール。

詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。

## <a name="return-value"></a>戻り値

**vprintf 系**と**vwprintf**出力エラーが発生した場合に、終端の null 文字または負の値をしないなど、書き込まれる文字数を返します。 場合*形式*null ポインター、または書式指定文字列に無効な書式指定文字が含まれている場合、無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は-1 を返し設定と**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

これらの各関数、引数リストへのポインターを受け取る書式設定して、特定のデータを書き込みます**stdout**します。

**vwprintf**のワイド文字バージョンは、 **vprintf**; 2 つの関数は、動作、ストリームが ANSI モードで開かれている場合は同じです。 **vprintf 系**UNICODE ストリームへの出力をサポートされていません。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。 無効な形式の文字列が検出されて、エラーとなることに注意してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf**|**vprintf**|**vprintf**|**vwprintf**|
|**_vtprintf_l**|**_vprintf_l**|**_vprintf_l**|**_vwprintf_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**vprintf 系**、 **_vprintf_l**|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|
|**vwprintf**、 **_vwprintf_l**|\<stdio.h> または \<wchar.h>、および \<stdarg.h>|\<varargs.h>*|

\* UNIX V との互換性用。

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 系関数](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
