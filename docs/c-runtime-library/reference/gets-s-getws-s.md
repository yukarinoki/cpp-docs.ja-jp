---
title: gets_s、_getws_s
ms.date: 4/2/2020
api_name:
- _getws_s
- gets_s
- _o__getws_s
- _o_gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getws_s
- gets_s
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
ms.openlocfilehash: aac64a42a2979623f4314f7bf28d7e4917eaee18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344217"
---
# <a name="gets_s-_getws_s"></a>gets_s、_getws_s

**stdin**ストリームから行を取得します。 これらの [gets および _getws](../../c-runtime-library/gets-getws.md) のバージョンは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」(CRT のセキュリティ機能) で説明されているように、セキュリティが強化されています。

## <a name="syntax"></a>構文

```C
char *gets_s(
   char *buffer,
   size_t sizeInCharacters
);
wchar_t *_getws_s(
   wchar_t *buffer,
   size_t sizeInCharacters
);
```

```cpp
template <size_t size>
char *gets_s( char (&buffer)[size] ); // C++ only

template <size_t size>
wchar_t *_getws_s( wchar_t (&buffer)[size] ); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
入力文字列の格納場所。

*sizeInCharacters*<br/>
バッファーのサイズ。

## <a name="return-value"></a>戻り値

成功した場合*はバッファを*返します。 エラーが発生した場合またはファイルの終端に達した場合は、**NULL** ポインターを返します。 どちらが発生したかを確認するには、 [ferror](ferror.md) または [feof](feof.md) を使用します。

## <a name="remarks"></a>解説

**gets_s**関数は、標準入力ストリーム**stdin**から行を読み取り、*それを buffer*に格納します。 行は、最初の改行文字 ('\n') までのすべての文字 (改行文字を含む) で構成されます。 **gets_s**改行文字を null 文字 ('\0') に置き換えた後、行を返します。 これに対し **、fgets_s**関数は改行文字を保持します。

最初の文字読み込み文字がファイルの終わり文字の場合は、*バッファー*の先頭に NULL 文字が格納され **、NULL**が戻されます。

**_getws_s**は **、gets_s**のワイド文字バージョンです。引数と戻り値はワイド文字列です。

*バッファー*が**NULL**または*sizeInCharacters*が 0 以下の場合、またはバッファーが小さすぎて入力行と NULL 終端文字を含めることができなか、これらの関数は、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)で説明されているように無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、これらの関数は**NULL を**返し、errno を**ERANGE**に設定します。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**gets_s**|\<stdio.h>|
|**_getws_s**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールはサポートされていません。 コンソール **、stdin 、stdout**、および**stdout****stderr**に関連付けられている標準ストリーム ハンドルは、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_gets_s.c
// This program retrieves a string from the stdin and
// prints the same string to the console.

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets_s( line, 20 );
   printf( "The line entered was: %s\n", line );
}
```

```Input
Hello there!
```

```Output
The line entered was: Hello there!
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[取得, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets、fgetws](fgets-fgetws.md)<br/>
[fputs、fputws](fputs-fputws.md)<br/>
[puts、_putws](puts-putws.md)<br/>
