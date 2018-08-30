---
title: _vcprintf_p、_vcprintf_p_l、_vcwprintf_p、_vcwprintf_p_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _vcprintf_p
- _vcwprintf_p_l
- _vcprintf_p_l
- _vcwprintf_p
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
- vcwprintf_p
- vcprintf_p_l
- _vcprintf_p
- _vcprintf_p_l
- vcwprintf_p_l
- vcprintf_p
- _vcwprintf_p
- _vcwprintf_p_l
dev_langs:
- C++
helpviewer_keywords:
- _vtcprintf_p_l function
- vcprintf_p_l function
- _vcprintf_p_l function
- vtcprintf_p_l function
- vcprintf_p function
- _vcwprintf_p function
- _vcprintf_p function
- vcwprintf_p function
- vcwprintf_p_l function
- vtcprintf_p function
- _vcwprintf_p_l function
- _vtcprintf_p function
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0e2271093237fbfdbc7f5e0492b1db220c469d1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210362"
---
# <a name="vcprintfp-vcprintfpl-vcwprintfp-vcwprintfpl"></a>_vcprintf_p、_vcprintf_p_l、_vcwprintf_p、_vcwprintf_p_l

引数リストへのポインターを使用して書式設定された出力をコンソールに書き込みます。書式指定文字列では、位置指定パラメーターがサポートされます。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _vcprintf_p(
   const char* format,
   va_list argptr
);
int _vcprintf_p_l(
   const char* format,
   locale_t locale,
   va_list argptr
);
int _vcwprintf_p(
   const wchar_t* format,
   va_list argptr
);
int _vcwprintf_p_l(
   const wchar_t* format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>パラメーター

*format*<br/>
書式指定。

*定義されています*<br/>
引数リストへのポインター。

*locale*<br/>
使用するロケール。

詳細については、「[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」をご覧ください。

## <a name="return-value"></a>戻り値

書き込まれた文字数。出力エラーが発生した場合は負の値が返されます。 場合*形式*null ポインターの場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** -1 が返されます。

## <a name="remarks"></a>Remarks

これらの各関数は、引数リストへのポインターを使用し、使用、 **_putch**関数を書式設定し、指定されたデータをコンソールに書き込みます。 (**_vcwprintf_p**使用 **_putwch**の代わりに **_putch**します。 **_vcwprintf_p**のワイド文字バージョンは、 **_vcprintf_p**します。 引数としてワイド文字列を使用します。)

これらの関数がのバージョン、 **_l**現在のロケールの代わりに渡されるロケール パラメーターを使用することを除き、サフィックスは同じです。

各*引数*(ある場合) は変換され、出力に対応する書式指定に応じて*形式*します。 書式指定では位置指定パラメーターがサポートされるので、書式指定文字列の中で引数を使用する順序を指定できます。 詳細については、「[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」をご覧ください。

これらの関数では、出力時にライン フィード文字をキャリッジ リターンとライン フィード (CR-LF) の組み合わせに変換しません。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

これらの関数は、入力ポインターと書式指定文字列を検証します。 場合*形式*または*引数*は**NULL**の説明に従って、これらの関数が、無効なパラメーター ハンドラーを呼び出します書式指定文字列に無効な書式指定文字が含まれている場合、または[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返し設定と**errno**に**EINVAL**します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_vtcprintf_p**|**_vcprintf_p**|**_vcprintf_p**|**_vcwprintf_p**|
|**_vtcprintf_p_l**|**_vcprintf_p_l**|**_vcprintf_p_l**|**_vcwprintf_p_l**|

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_vcprintf_p**、 **_vcprintf_p_l**|\<conio.h> および \<stdarg.h>|
|**_vcwprintf_p**、 **_vcwprintf_p_l**|\<conio.h> および \<stdarg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_vcprintf_p.c
// compile with: /c
#include <conio.h>
#include <stdarg.h>

// An error formatting function that's used to print to the console.
int eprintf(const char* format, ...)
{
   va_list args;
   va_start(args, format);
   int result = _vcprintf_p(format, args);
   va_end(args);
   return result;
}

int main()
{
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",
      "one", 222);
   _cprintf_s("%d characters printed\r\n");
}
```

```Output
parameter 2 = 222; parameter 1 = one
38 characters printed
```

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf、_cprintf_l、_cwprintf、_cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
