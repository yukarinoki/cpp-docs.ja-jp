---
title: putchar、putwchar
ms.date: 11/04/2016
apiname:
- putchar
- putwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- putchar
- putwchar
- _puttchar
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
ms.openlocfilehash: becee3d79f58ac018d1161c1af36e9a4646640bf
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327058"
---
# <a name="putchar-putwchar"></a>putchar、putwchar

**stdout** に文字を出力します。

## <a name="syntax"></a>構文

```C
int putchar(
   int c
);
wint_t putwchar(
   wchar_t c
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
書き込む文字。

## <a name="return-value"></a>戻り値

書き込まれた文字を返します。 エラーまたはファイルの終わりの状態を示す**putc**と**putchar**返す**EOF**;**putwc**と**putwchar**返す**WEOF**します。 4 つすべてのルーチンで、[ferror](ferror.md) または [feof](feof.md) を使用して、エラーまたはファイルの終端を確認します。 Null ポインターを渡された場合*ストリーム*、」の説明に従って、これらの関数は、無効なパラメーター例外を生成[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 返されるかどうかは、引き続き実行が許可された、 **EOF**または**WEOF**設定と**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Putc**ルーチンは、1 つの文字を書き込みます*c*出力に*ストリーム*現在の位置。 任意の整数を渡すことが**putc**が下位の 8 ビットのみに書き込まれます。 **Putchar**ルーチンと同じ`putc( c, stdout )`します。 各ルーチンでは、読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。 **putc**と**putchar**のような**fputc**と **_fputchar**、それぞれ、関数およびマクロとして実装されますが、(を参照してください[関数とマクロの使い分け](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md))。 **putwc**と**putwchar**のワイド文字バージョン**putc**と**putchar**、それぞれします。

**_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttchar**|**putchar**|**putchar**|**putwchar**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**putchar**|\<stdio.h>|
|**putwchar**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_putchar.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;

   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putchar( *p );
}
```

### <a name="output"></a>出力

```Output
This is the line of output
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fputc、fputwc](fputc-fputwc.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
