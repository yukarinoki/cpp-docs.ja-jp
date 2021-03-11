---
description: '詳細については、次を参照してください: _vfprintf_p、_vfprintf_p_l、_vfwprintf_p、_vfwprintf_p_l'
title: _vfprintf_p、_vfprintf_p_l、_vfwprintf_p、_vfwprintf_p_l
ms.date: 3/9/2021
api_name:
- _vfprintf_p
- _vfwprintf_p
- _vfprintf_p_l
- _vfwprintf_p_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vfwprintf_p_l
- _vfprintf_p
- vfwprintf_p_l
- vfwprintf_p
- vfprintf_p_l
- _vfwprintf_p
- _vftprintf_p
- _vfprintf_p_l
- vfprintf_p
helpviewer_keywords:
- vfprintf_p_l function
- _vftprintf_p_l function
- _vfprintf_p function
- vfprintf_p function
- vftprintf_p_l function
- _vfprintf_p_l function
- _vftprintf_p function
- _vfwprintf_p_l function
- vfwprintf_p_l function
- _vfwprintf_p function
- vftprintf_p function
- formatted text [C++]
- vfwprintf_p function
ms.openlocfilehash: 5aa305a506c6dc046fe4b828e7d693ad278f0daa
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "102621477"
---
# <a name="_vfprintf_p-_vfprintf_p_l-_vfwprintf_p-_vfwprintf_p_l"></a>_vfprintf_p、_vfprintf_p_l、_vfwprintf_p、_vfwprintf_p_l

引数リストへのポインターを使用して、書式付き出力を書き込みます。その際、書式指定文字列で引数を使用する順序を指定できます。

## <a name="syntax"></a>構文

```C
int _vfprintf_p(
   FILE *stream,
   const char *format,
   va_list argptr
);
int _vfprintf_p_l(
   FILE *stream,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vfwprintf_p(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
int _vfwprintf_p_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>パラメーター

*一連*<br/>
**FILE** 構造体へのポインター。

*format*<br/>
書式の指定。

*argptr*<br/>
引数リストへのポインター。

*locale*<br/>
使用するロケール。

詳細については、[書式の指定](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)に関する記事をご覧ください。

## <a name="return-value"></a>戻り値

**_vfprintf_p** と **_vfwprintf_p** は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値が返されます。

## <a name="remarks"></a>注釈

これらの各関数は、引数リストへのポインターを受け取り、指定されたデータを書式設定して *ストリーム* に書き込みます。 これらの関数は、位置指定パラメーターをサポートしている点でのみ、 **_vfprint_s** と **_vfwprint_s** のバージョンとは異なります。 詳細については、「[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」を参照してください。

**_vfwprintf_p** は **_vprintf_p** のワイド文字バージョンです。ストリームが ANSI モードで開かれている場合、2つの関数の動作は同じになります。 **_vprintf_p** は、現在 UNICODE ストリームへの出力をサポートしていません。

**_L** サフィックスを持つこれらの関数のバージョンは、現在のスレッドロケールの代わりに渡されたロケールパラメーターを使用する点を除いて同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。
> Windows 10 バージョン 2004 (ビルド 19041) 以降では、 `printf` 関数ファミリは、丸め処理のために IEEE 754 の規則に従って、正確に表現可能な浮動小数点数を出力します。 以前のバージョンの Windows では、"5" で終わる厳密に表現可能な浮動小数点数は常に切り上げられます。 IEEE 754 では、最も近い偶数 ("銀行型丸め" とも呼ばれます) に丸める必要があることが示されています。 たとえば、との `printf("%1.0f", 1.5)` 両方 `printf("%1.0f", 2.5)` が2に丸められる必要があります。 以前は、1.5 は2に丸められ、2.5 は3に丸められていました。 この変更は、正確に表現できる数値にのみ影響します。 たとえば、2.35 (メモリで表される場合は2.35000000000000008 に近い) は、2.4 に切り上げられます。 これらの関数によって実行される丸め処理は、によって設定された浮動小数点丸めモードにも従い [`fesetround`](fegetround-fesetround2.md) ます。 以前は、常に丸め処理を選択していま `FE_TONEAREST` した。 この変更は、Visual Studio 2019 バージョン16.2 以降を使用してビルドされたプログラムにのみ影響します。 従来の浮動小数点丸め動作を使用するには、 [' legacy_stdio_float_rounding. .obj '](../link-options.md)にリンクします。

*ストリーム* または *形式* が null ポインターの場合、または書式指定文字列に無効な書式指定文字が含まれている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は-1 を返し、 **errno** を **EINVAL** に設定します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftprintf_p**|**_vfprintf_p**|**_vfprintf_p**|**_vfwprintf_p**|
|**_vftprintf_p_l**|**_vfprintf_p_l**|**_vfprintf_p_l**|**_vfwprintf_p_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_vfprintf_p**、 **_vfprintf_p_l**|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|
|**_vfwprintf_p**、 **_vfwprintf_p_l**|\<stdio.h> または \<wchar.h> 、 \<stdarg.h>|\<varargs.h>*|

\* UNIX V との互換性用。

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 関数](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、 \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
[位置指定パラメーターの printf_p](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[_fprintf_p、_fprintf_p_l、_fwprintf_p、_fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[_vsprintf_p、_vsprintf_p_l、_vswprintf_p、_vswprintf_p_l](vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)<br/>
[_sprintf_p、_sprintf_p_l、_swprintf_p、_swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
