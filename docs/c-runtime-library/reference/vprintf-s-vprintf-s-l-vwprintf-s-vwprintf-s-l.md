---
title: vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _vwprintf_s_l
- vwprintf_s
- _vprintf_s_l
- vprintf_s
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
- vprintf_s
- vwprintf_s
- _vtprintf_s
dev_langs:
- C++
helpviewer_keywords:
- vwprintf_s_l function
- _vwprintf_s_l function
- vwprintf_s function
- _vtprintf_s_l function
- vprintf_s_l function
- vtprintf_s_l function
- _vtprintf_s function
- vtprintf_s function
- _vprintf_s_l function
- formatted text [C++]
- vprintf_s function
ms.assetid: cf864996-a530-4b40-9c30-54c4cef439c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e1c8f2780fb9a6b65c60c0622526020a13f74e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415596"
---
# <a name="vprintfs-vprintfsl-vwprintfs-vwprintfsl"></a>vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらのバージョンの [vprintf、_vprintf_l、vwprintf、_vwprintf_l](vprintf-vprintf-l-vwprintf-vwprintf-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。

## <a name="syntax"></a>構文

```C
int vprintf_s(
   const char *format,
   va_list argptr
);
int _vprintf_s_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int vwprintf_s(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_s_l(
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

**vprintf_s**と**vwprintf_s**を含まない終端の null 文字または負の値の出力エラーが発生した場合、書き込まれる文字数を返します。 場合*形式*null ポインター、または書式指定文字列に無効な書式指定文字が含まれている場合、無効なパラメーター ハンドラーが呼び出される、」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は-1 を返します設定と**errno**に**EINVAL**です。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

これらの各関数は、引数リストへのポインターをとり書式化してに指定されたデータを書き込む**stdout**です。

これらの関数のセキュリティで保護されたバージョンが異なる**vprintf**と**vwprintf**その内のみで、安全なバージョンを確認して、書式指定文字列に有効な書式指定文字が含まれています。

**vwprintf_s**のワイド文字バージョンは、 **vprintf_s**; ストリームが ANSI モードで開かれている場合、2 つの関数動作は同じです。 **vprintf_s** UNICODE ストリームへの出力はサポートされていません。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf_s**|**vprintf_s**|**vprintf_s**|**vwprintf_s**|
|**_vtprintf_s_l**|**_vprintf_s_l**|**_vprintf_s_l**|**_vwprintf_s_l**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**vprintf_s**、 **_vprintf_s_l**|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|
|**vwprintf_s**、 **_vwprintf_s_l**|\<stdio.h> または \<wchar.h>、および \<stdarg.h>|\<varargs.h>*|

\* UNIX V との互換性用。

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 系関数](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
