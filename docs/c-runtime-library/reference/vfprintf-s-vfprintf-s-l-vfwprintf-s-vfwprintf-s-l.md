---
title: vfprintf_s、_vfprintf_s_l、vfwprintf_s、_vfwprintf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vfwprintf_s
- _vfprintf_s_l
- vfprintf_s
- _vfwprintf_s_l
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
- _vftprintf_s
- vfwprintf_s
- vfprintf_s
dev_langs:
- C++
helpviewer_keywords:
- vfprintf_s_l function
- vfwprintf_s_l function
- vfwprintf_s function
- _vfprintf_s_l function
- _vfwprintf_s_l function
- vftprintf_s_l function
- vfprintf_s function
- _vftprintf_s_l function
- formatted text [C++]
- _vftprintf_s function
ms.assetid: eab6f563-46e2-4806-963f-2b23f339ecdc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f1c9d6bde39fcd763416e4c8dd50f0b756cb6b4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220296"
---
# <a name="vfprintfs-vfprintfsl-vfwprintfs-vfwprintfsl"></a>vfprintf_s、_vfprintf_s_l、vfwprintf_s、_vfwprintf_s_l

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [vfprintf、_vfprintf_l、vfwprintf、_vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md) です。

## <a name="syntax"></a>構文

```C
int vfprintf_s(
   FILE *stream,
   const char *format,
   va_list argptr
);
int _vfprintf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale,
   va_list argptr
);
int vfwprintf_s(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
int _vfwprintf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*format*<br/>
書式の指定。

*定義されています*<br/>
引数リストへのポインター。

*locale*<br/>
使用するロケール。

詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。

## <a name="return-value"></a>戻り値

**vfprintf_s**と**vfwprintf_s**出力エラーが発生した場合に、終端の null 文字または負の値をしないなど、書き込まれる文字数を返します。 いずれか*ストリーム*または*形式*null ポインター、または書式指定文字列に無効な書式指定文字が含まれている場合、無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は-1 を返し設定と**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

これらの各関数、引数リストへのポインターを受け取る書式設定して、特定のデータを書き込みます*ストリーム*します。

これらの関数は、セキュリティで保護されたバージョンを確認することでのみ、保護されていないバージョンとは異なります。、*形式*文字列に有効な書式指定文字が含まれています。

**vfwprintf_s**のワイド文字バージョンは、 **vfprintf_s**; 2 つの関数は、動作、ストリームが ANSI モードで開かれている場合は同じです。 **vfprintf_s** UNICODE ストリームへの出力をサポートされていません。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftprintf_s**|**vfprintf_s**|**vfprintf_s**|**vfwprintf_s**|
|**_vftprintf_s_l**|**_vfprintf_s_l**|**_vfprintf_s_l**|**_vfwprintf_s_l**|

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**vfprintf_s**、 **_vfprintf_s_l**|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|
|**vfwprintf_s**、 **_vfwprintf_s_l**|\<stdio.h> または \<wchar.h>、および \<stdarg.h>|\<varargs.h>*|

\* UNIX V との互換性用。

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 系関数](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
