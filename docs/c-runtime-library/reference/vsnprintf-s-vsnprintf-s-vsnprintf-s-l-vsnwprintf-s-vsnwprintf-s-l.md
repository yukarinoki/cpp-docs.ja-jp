---
title: vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l
ms.date: 11/04/2016
api_name:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
helpviewer_keywords:
- vsnwprintf_s function
- _vsntprintf_s function
- _vsntprintf_s_l function
- vsntprintf_s function
- vsnwprintf_s_l function
- vsnprintf_s_l function
- vsntprintf_s_l function
- _vsnwprintf_s_l function
- _vsnprintf_s function
- vsnprintf_s function
- _vsnprintf_s_l function
- _vsnwprintf_s function
- formatted text [C++]
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
ms.openlocfilehash: edb534eb533d63c9298b7b7e9aced1be3e8652d9
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502795"
---
# <a name="vsnprintf_s-_vsnprintf_s-_vsnprintf_s_l-_vsnwprintf_s-_vsnwprintf_s_l"></a>vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) です。

## <a name="syntax"></a>構文

```C
int vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int _vsnprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>パラメーター

*格納*<br/>
出力の格納位置。

*sizeOfBuffer*<br/>
出力 *バッファー* のサイズ (文字数)。

*count*<br/>
書き込む最大文字数 (終端の null は含まない)、または [_TRUNCATE](../../c-runtime-library/truncate.md)。

*format*<br/>
書式の指定。

*argptr*<br/>
引数リストへのポインター。

*locale*<br/>
使用するロケール。

詳細については、[書式の指定](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)に関する記事をご覧ください。

## <a name="return-value"></a>戻り値

**vsnprintf_s**、 **_vsnprintf_s** と **_vsnwprintf_s** は、書き込まれた文字数を返します (終端の null は含まれません)。または、データの切り捨てまたは出力エラーが発生した場合は負の値が返されます。

* *Count*が*sizeOfBuffer*未満で、データの文字数が*count*以下の場合、または*count*が[_TRUNCATE](../../c-runtime-library/truncate.md)で、データの文字数が*sizeOfBuffer*未満の場合は、すべてのデータが書き込まれ、文字数が返されます。

* *Count*が*sizeOfBuffer*未満であるにもかかわらず、データが*カウント*文字を超えている場合は、最初の*カウント*文字が書き込まれます。 残りのデータの切り捨てが発生し、無効なパラメーターハンドラーを呼び出さずに-1 が返されます。

* *Count*が[_TRUNCATE](../../c-runtime-library/truncate.md)で、データの文字数がまたは*sizeOfBuffer*を超えている場合は、*バッファー*に格納されている文字列の多く (終端の null を含む) が書き込まれます。 残りのデータの切り捨てが発生し、無効なパラメーターハンドラーを呼び出さずに-1 が返されます。

* *Count*が*sizeOfBuffer*に等しいか、またはデータの文字数が*sizeOfBuffer*未満の場合は、すべてのデータが書き込まれ (終端の null を含む)、文字数が返されます。

* *Count*とデータの文字数が両方とも等しいか、または*sizeOfBuffer*を超える場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 無効なパラメーターハンドラーの後に実行が継続する場合、これらの関数は *buffer* を空の文字列に設定し、 **errno** を **ERANGE**に設定し、-1 を返します。

* *バッファー*または*形式*が**NULL**ポインターの場合、または*count*が0以下の場合は、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は **errno** を **EINVAL** に設定し、-1 を返します。

### <a name="error-conditions"></a>エラー条件

|**Condition**|戻り値|**errno**|
|-----------------|------------|-------------|
|*バッファー*が**NULL**です|-1|**EINVAL**|
|*形式*が**NULL**です|-1|**EINVAL**|
|*カウント* <= 0|-1|**EINVAL**|
|*sizeOfBuffer* が小さすぎます (および *count* ! = **_TRUNCATE**)|-1 (および空の文字列に設定された *バッファー* )|**ERANGE**|

## <a name="remarks"></a>注釈

**vsnprintf_s** は **_vsnprintf_s**と同じです。 ANSI 規格に準拠するために**vsnprintf_s**が含まれています。 **_vnsprintf** は旧バージョンとの互換性のために残されています。

これらの各関数は、引数リストへのポインターを受け取り、指定されたデータの文字 *数* を、 *バッファー* によって示されるメモリに書式設定して書き込み、終端の null を追加します。

*Count*が[_TRUNCATE](../../c-runtime-library/truncate.md)場合、これらの関数は*バッファー*に収まる限りの文字列を書き込みますが、終端の null を格納するための領域を残します。 (終端の null を含む) 文字列全体が *バッファー*に格納されている場合、これらの関数は書き込まれた文字数を返します (終端の null は含まれません)。それ以外の場合、これらの関数は、切り捨てが発生したことを示す-1 を返します。

**_L**サフィックスを持つこれらの関数のバージョンは、現在のスレッドロケールの代わりに渡されたロケールパラメーターを使用する点を除いて同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

> [!NOTE]
> 終端の null 用の空き領域があることを確認するには、 *count* がバッファーの長さより厳密に小さいことを確認するか、 **_TRUNCATE**を使用します。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|
|**_vsnprintf_s**、 **_vsnprintf_s_l**|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|
|**_vsnwprintf_s**、 **_vsnwprintf_s_l**|\<stdio.h> または \<wchar.h> 、 \<stdarg.h>|\<varargs.h>*|

\* UNIX V との互換性用。

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```cpp
// crt_vsnprintf_s.cpp
#include <stdio.h>
#include <wtypes.h>

void FormatOutput(LPCSTR formatstring, ...)
{
   int nSize = 0;
   char buff[10];
   memset(buff, 0, sizeof(buff));
   va_list args;
   va_start(args, formatstring);
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);
   printf("nSize: %d, buff: %s\n", nSize, buff);
   va_end(args);
}

int main() {
   FormatOutput("%s %s", "Hi", "there");
   FormatOutput("%s %s", "Hi", "there!");
   FormatOutput("%s %s", "Hi", "there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 関数](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、 \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
