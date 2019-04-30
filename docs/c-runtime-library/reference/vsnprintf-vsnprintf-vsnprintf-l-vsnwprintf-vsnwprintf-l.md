---
title: vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l
ms.date: 11/04/2016
apiname:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
ms.openlocfilehash: 7c3416397d8f43963d3be2ce9bc39707ea7865db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383465"
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらの関数のセキュリティを強化したバージョンを使用できます。「[vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l](vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
出力の格納位置。

*count*<br/>
書き込む最大文字数。

*format*<br/>
書式の指定。

*argptr*<br/>
引数リストへのポインター。

*locale*<br/>
使用するロケール。

詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。

## <a name="return-value"></a>戻り値

**Vsnprintf**関数は終端の null 文字をカウントせず、書き込まれる文字の数を返します。 バッファー サイズを指定して場合*カウント*で指定された出力を格納する十分な大きさでない*形式*と*定義されています*の戻り値**vsnprintf**記述がない場合、null 文字をカウントする文字数は、*カウント*が十分な大きさであった。 戻り値がより大きい場合*カウント*- 1 の場合、出力が切り捨てられました。 戻り値 -1 は、エンコード エラーが発生したことを示します。

両方 **_vsnprintf**と **_vsnwprintf**関数は、書き込む文字数に等しいまたはそれよりも小さいが書き込まれた文字数を返す*カウント*番号。書き込む文字がより大きい*カウント*、これら関数は出力が切り捨てられたことを示す戻り値の-1。

これらすべての関数によって返される値には、書き込まれているかどうかを問わず、終端の null は含まれません。 ときに*カウント*が 0 の場合は、関数は書き込みの文字の数など、終端の null 値が返されます。 この結果を用いて文字列と終端の null に対して十分なバッファー領域を割り当て、関数を再び呼び出してバッファーを埋めることができます。

場合*形式*は**NULL**、または*バッファー*は**NULL**と*数*、これらの関数は 0 と等しくないです。」の説明に従って、無効なパラメーター ハンドラーを呼び出す[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返し設定と**errno**に**EINVAL**します。

## <a name="remarks"></a>Remarks

これらの各関数は、引数リストへのポインターを使用、データを書式設定して最大書き込みます*カウント*によって示されるメモリへの文字*バッファー*します。 **Vsnprintf**関数は、出力が切り捨てられる場合でも常に、null 終端記号を書き込みます。 使用する場合 **_vsnprintf**と **_vsnwprintf**、バッファーは null で終わります最後に余裕がある場合にのみ (書き込む文字数の場合より小さい*カウント*).

> [!IMPORTANT]
> 特定の種類のセキュリティ上のリスクを回避する*形式*ユーザー定義文字列ではありません。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

> [!NOTE]
> 呼び出すときに、終端の null 用の空きが認識されていることを確認する **_vsnprintf**、 **_vsnprintf_l**、 **_vsnwprintf**と **_vsnwprintf_l**ことを確認します、*カウント*はバッファーの長さより厳密に小さいと、関数を呼び出す前に null にバッファーを初期化します。
>
> **Vsnprintf**終端の null を常に書き込み、*カウント*パラメーター バッファーのサイズに等しい場合があります。

Visual Studio 2015 と Windows 10 で UCRT と共に開始**vsnprintf**と同じですが不要になった **_vsnprintf**します。 **Vsnprintf**関数は C99 規格に準拠 **_vnsprintf**以前の Visual Studio code との下位互換性は保持されます。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf**|**_vsnprintf**|**_vsnprintf**|**_vsnwprintf**|
|**_vsntprintf_l**|**_vsnprintf_l**|**_vsnprintf_l**|**_vsnwprintf_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**vsnprintf**、 **_vsnprintf**、 **_vsnprintf_l**|\<stdio.h>|\<stdio.h> または \<cstdio>|
|**_vsnwprintf**、 **_vsnwprintf_l**|\<stdio.h> または \<wchar.h>|\<stdio.h>、\<wchar.h>、\<cstdio>、または \<cwchar>|

**_Vsnprintf**、 **_vsnprintf_l**、 **_vsnwprintf**と **_vsnwprintf_l**関数は、Microsoft 固有の仕様。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_vsnwprintf.c
// compile by using: cl /W3 crt_vsnwprintf.c

// To turn off error C4996, define this symbol:
#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <wtypes.h>

#define BUFFCOUNT (10)

void FormatOutput(LPCWSTR formatstring, ...)
{
    int nSize = 0;
    wchar_t buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput(L"%ls %ls", L"Hi", L"there");
    FormatOutput(L"%ls %ls", L"Hi", L"there!");
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

代わりに vsnprintf を使用し、パラメータに小さな文字列を指定すると、挙動が変化します。 *カウント*パラメーターは、バッファーの全体サイズを指定でき、戻り値が書き込まれた場合の文字数は、*カウント*サイズが十分で。

## <a name="example"></a>例

```C
// crt_vsnprintf.c
// compile by using: cl /W4 crt_vsnprintf.c
#include <stdio.h>
#include <stdarg.h> // for va_list, va_start
#include <string.h> // for memset

#define BUFFCOUNT (10)

void FormatOutput(char* formatstring, ...)
{
    int nSize = 0;
    char buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);
    printf("nSize: %d, buff: %s\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: 10, buff: Hi there!
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 系関数](../../c-runtime-library/vprintf-functions.md)<br/>
[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
