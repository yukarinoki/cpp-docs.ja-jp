---
description: '詳細については、次を参照してください: _cprintf_p、_cprintf_p_l、_cwprintf_p、_cwprintf_p_l'
title: _cprintf_p、_cprintf_p_l、_cwprintf_p、_cwprintf_p_l
ms.date: 3/9/2021
api_name:
- _cprintf_p_l
- _cwprintf_p_l
- _cwprintf_p
- _cprintf_p
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
- cprintf_p
- cwprintf_p
- tcprintf_p
- _cwprintf_p_l
- _cprintf_p
- csprintf_p_l
- _cprintf_p_l
- _cwprintf_p
- _tcprintf_p
- cprintf_p_l
helpviewer_keywords:
- _cwprintf_p_l function
- cwprintf_p function
- tcprintf_p_l function
- cprintf_p_l function
- _tcprintf_p function
- _tcprintf_p_l function
- _cprintf_p function
- _cprintf_p_l function
- cwprintf_p_l function
- _cwprintf_p function
- tcprintf_p function
- cprintf_p function
ms.openlocfilehash: 155e6d0a9842c7ade999979e44418eecd5fd0439
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "102621907"
---
# <a name="_cprintf_p-_cprintf_p_l-_cwprintf_p-_cwprintf_p_l"></a>_cprintf_p、_cprintf_p_l、_cwprintf_p、_cwprintf_p_l

書式化してコンソールに出力します。書式指定文字列で位置指定パラメーターをサポートしています。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _cprintf_p(
   const char * format [,
   argument] ...
);
int _cprintf_p_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_p(
   const wchar * format [,
   argument] ...
);
int _cwprintf_p_l(
   const wchar * format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>パラメーター

*format*<br/>
書式指定文字列。

*argument*<br/>
省略可能なパラメーター。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

出力した文字数。エラーが発生した場合は負の値を返します。

## <a name="remarks"></a>注釈

これらの関数は、一連の文字および値を書式設定してコンソールに直接出力します。その際、 **_putch** 関数と **_putwch** 関数を使用して文字を出力します。 各 *引数*(存在する場合) は、対応する書式指定に従って変換および出力さ *れます。* 形式は、 [printf_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)関数の *format* パラメーターと同じ形式と機能を持ちます。 **_Cprintf_p** と **cprintf_s** の違いは、 **_cprintf_p** が位置指定パラメーターをサポートしていることです。これにより、書式設定文字列で引数が使用される順序を指定できます。 詳細については、「[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」を参照してください。

**Fprintf_p**、 **printf_p**、および **sprintf_p** 関数とは異なり、では、出力時にラインフィードの文字が復帰と改行 (cr-lf) の組み合わせに変換されることはあり **_cwprintf_p** **_cprintf_p** ません。 重要な違いは、 **_cwprintf_p** では、Windows NT で使用する場合に Unicode 文字が表示されるという点です。 **_Cprintf_p** とは異なり、 **_cwprintf_p** は現在のコンソールのロケール設定を使用します。

**_L** サフィックスを持つこれらの関数のバージョンは、現在のロケールの代わりに渡されたロケールパラメーターを使用する点を除いて同じです。

また、 **_cprintf_s** や **_cwprintf_s** と同様に、入力ポインターと書式指定文字列を検証します。 *Format* または *引数* が **NULL** の場合、または書式指定文字列に無効な書式指定文字が含まれている場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は-1 を返し、 **errno** を **EINVAL** に設定します。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。
>
>
> Windows 10 バージョン 2004 (ビルド 19041) 以降では、 `printf` 関数ファミリは、丸め処理のために IEEE 754 の規則に従って、正確に表現可能な浮動小数点数を出力します。 以前のバージョンの Windows では、"5" で終わる厳密に表現可能な浮動小数点数は常に切り上げられます。 IEEE 754 では、最も近い偶数 ("銀行型丸め" とも呼ばれます) に丸める必要があることが示されています。 たとえば、との `printf("%1.0f", 1.5)` 両方 `printf("%1.0f", 2.5)` が2に丸められる必要があります。 以前は、1.5 は2に丸められ、2.5 は3に丸められていました。 この変更は、正確に表現できる数値にのみ影響します。 たとえば、2.35 (メモリで表される場合は2.35000000000000008 に近い) は、2.4 に切り上げられます。 これらの関数によって実行される丸め処理は、によって設定された浮動小数点丸めモードにも従い [`fesetround`](fegetround-fesetround2.md) ます。 以前は、常に丸め処理を選択していま `FE_TONEAREST` した。 この変更は、Visual Studio 2019 バージョン16.2 以降を使用してビルドされたプログラムにのみ影響します。 従来の浮動小数点丸め動作を使用するには、をにリンク [`legacy_stdio_float_rounding.obj`](../link-options.md) します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_p**|**_cprintf_p**|**_cprintf_p**|**_cwprintf_p**|
|**_tcprintf_p_l**|**_cprintf_p_l**|**_cprintf_p_l**|**_cwprintf_p_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_cprintf_p**、 **_cprintf_p_l**|\<conio.h>|
|**_cwprintf_p**、 **_cwprintf_p_l**|\<conio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_cprintf_p.c
// This program displays some variables to the console
// using the _cprintf_p function.

#include <conio.h>

int main( void )
{
    int         i = -16,
                h = 29;
    unsigned    u = 62511;
    char        c = 'A';
    char        s[] = "Test";

    // Note that console output does not translate
    // \n as standard output does. Use \r\n instead.
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",
                h, i, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf、_cscanf_l、_cwscanf、_cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[_cscanf_s、_cscanf_s_l、_cwscanf_s、_cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[_fprintf_p、_fprintf_p_l、_fwprintf_p、_fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[_printf_p、_printf_p_l、_wprintf_p、_wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_sprintf_p、_sprintf_p_l、_swprintf_p、_swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[_vfprintf_p、_vfprintf_p_l、_vfwprintf_p、_vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_cprintf_s、_cprintf_s_l、_cwprintf_s、_cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[位置指定パラメーターの printf_p](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
