---
title: sprintf、_sprintf_l、swprintf、_swprintf_l、__swprintf_l
ms.date: 11/04/2016
apiname:
- __swprintf_l
- sprintf
- _sprintf_l
- _swprintf_l
- swprintf
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _stprintf_l
- __swprintf_l
- sprintf_l
- swprintf
- _sprintf_l
- sprintf
- _stprintf
- stprintf_l
helpviewer_keywords:
- _swprintf_l function
- _stprintf function
- __swprintf_l function
- stprintf function
- sprintf function
- _sprintf_l function
- _stprintf_l function
- swprintf function
- strings [C++], writing to
- _CRT_NON_CONFORMING_SWPRINTFS
- swprintf_l function
- stprintf_l function
- sprintf_l function
- formatted text [C++]
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
ms.openlocfilehash: f32b1622539e73ab04c19d6d46ffdbc58b9961d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354874"
---
# <a name="sprintf-sprintfl-swprintf-swprintfl-swprintfl"></a>sprintf、_sprintf_l、swprintf、_swprintf_l、__swprintf_l

文字列に書式付きデータを書き込みます。 これらの関数のセキュリティを強化したバージョンについては、「[sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)」をご覧ください。 セキュリティで保護されたバージョンの**swprintf**と **_swprintf_l**受け取らない、*カウント*パラメーター。

## <a name="syntax"></a>構文

```C
int sprintf(
   char *buffer,
   const char *format [,
   argument] ...
);
int _sprintf_l(
   char *buffer,
   const char *format,
   locale_t locale [,
   argument] ...
);
int swprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument]...
);
int _swprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
int __swprintf_l(
   wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int sprintf(
   char (&buffer)[size],
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _sprintf_l(
   char (&buffer)[size],
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
出力の格納場所。

*count*<br/>
この関数の Unicode バージョンで格納する最大文字数。

*format*<br/>
書式指定文字列。

*argument*<br/>
省略可能な引数。

*locale*<br/>
使用するロケール。

詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。

## <a name="return-value"></a>戻り値

エラーが発生した場合は-1 または書き込まれた文字数。 場合*バッファー*または*形式*null ポインターの場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返し設定と**errno**に**EINVAL**します。

**sprintf**に格納されるバイト数を返します*バッファー*、終端の null 文字を含みません。 **swprintf**で格納されるワイド文字の数を返します*バッファー*、終端の null ワイド文字を含みません。

## <a name="remarks"></a>Remarks

**Sprintf**関数は、書式化して、一連の文字と値を格納*バッファー*します。 各*引数*(ある場合) は変換されに対応する書式指定に応じて*形式*します。 形式は、通常の文字と同じ形式し、機能、*形式*引数[printf](printf-printf-l-wprintf-wprintf-l.md)します。 最後に書き込まれる文字の後に NULL 文字が追加されます。 重なり合う文字列間でコピーした場合の動作は未定義です。

> [!IMPORTANT]
> 使用して**sprintf**、書き込まれた文字を使用してコードの数を制限する方法はありません**sprintf**バッファー オーバーランを受けやすくなります。 関連の関数の使用を検討[_snprintf](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)に書き込まれる文字の最大数を指定する*バッファー*、使用または[_scprintf](scprintf-scprintf-l-scwprintf-scwprintf-l.md)を決定する大きさをバッファーが必要です。 また、いることを確認*形式*ユーザー定義文字列ではありません。

**swprintf**のワイド文字バージョンは、 **sprintf**; へのポインター引数**swprintf**はワイド文字列です。 エンコーディング エラーの検出**swprintf**内で異なる場合があります**sprintf**します。 **swprintf**と**fwprintf**動作は同じことを除いて**swprintf**型の出力先ではなく文字列に出力を書き込む**ファイル**、および**swprintf**が必要です、*カウント*書き込まれる文字の最大数を指定するパラメーター。 これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

**swprintf** 、2 番目のパラメーターを必要とする ISO C 標準に準拠している*カウント*、型の**size_t**します。 古い非標準動作を強制的には、次のように定義します。**実行させるには**します。 この古い動作は、将来的には削除される可能性があるので、規格に準拠した新しい動作を使用するようにコードを変更する必要があります。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf**|**sprintf**|**sprintf**|**_swprintf**|
|**_stprintf_l**|**_sprintf_l**|**_sprintf_l**|**__swprintf_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**sprintf**、 **_sprintf_l**|\<stdio.h>|
|**swprintf**、 **_swprintf_l**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_sprintf.c
// compile with: /W3
// This program uses sprintf to format various
// data and place them in the string named buffer.

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996
   // Note: sprintf is deprecated; consider using sprintf_s instead

   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>例

```C
// crt_swprintf.c
// wide character example
// also demonstrates swprintf returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf、_scanf_l、wscanf、_wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf 系関数](../../c-runtime-library/vprintf-functions.md)<br/>
